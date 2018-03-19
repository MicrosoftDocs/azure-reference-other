---
title: "AVG (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: df66e28f-2098-4a64-ae11-f3339fad677d
caps.latest.revision: 7
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# AVG (U-SQL)
The AVG aggregator computes the average of a set of numeric values by dividing the sum of those values by the count of nonnull values. If the sum exceeds the maximum value for the data type of the return value an error will be returned. 

The identity value is null. 

<table><th align="left">Syntax</th><tr><td><pre>
AVG_Expression :=                                                                                        
      'AVG' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**  
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation.  

* <a name="exp"></a>**`expression`**  
The C# expression (including column references) that gets aggregated. The type of the expression has to be a numeric or nullable numeric type, otherwise an error is raised. 

### Return Type 
The return type is determined by the type of the evaluated result of the expression as follows: 

|Expression type|Return type|Comment| 
|---|---|---|
|Integral types (short, int, uint, etc) implicitly castable to long and long?| long?|To be aligned with SQL semantics. The resulting value will be truncated to its integral part.| 
|ulong, ulong?|double?|Returns double to be able to handle large values.| 
|decimal, decimal?|decimal?||
|float, float?, double, double?|double?||

### Usage in Windowing Expression 
This aggregator can be used in a [windowing expression](over-expression-u-sql.md) without any additional restrictions. 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  

   ```sql
   @employees = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",   "Engineering", 100, 10000),
        (2, "Sophia", "Engineering", 100, 20000),
        (3, "Liam",   "Engineering", 100, 30000),
        (4, "Emma",   "HR",          200, 10000),
        (5, "Jacob",  "HR",          200, 10000),
        (6, "Olivia", "HR",          200, 10000),
        (7, "Mason",  "Executive",   300, 50000),
        (8, "Ava",    "Marketing",   400, 15000),
        (9, "Ethan",  "Marketing",   400, 10000) 
        ) AS T(EmpID, EmpName, DeptName, DeptID, Salary);
   ```

**A.    Average of all values(`Salary`)**  
The following query determines the average salary 1) for all employees, and 2) from all DISTINCT salary values.
```sql
@result =
    SELECT AVG(Salary) AS AverageSalary,
           AVG(DISTINCT Salary) AS AverageDistinctSalary
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/avg/exampleA.csv"
USING Outputters.Csv();
```

**B.    Average values per group**  
The following query determines the average salary for each department with the [GROUP BY](group-by-and-having-clauses-u-sql.md) clause.
```sql
@result =
    SELECT DeptName,
           AVG(Salary) AS AverageSalaryByDept
    FROM @employees
    GROUP BY DeptName;

OUTPUT @result
TO "/Output/ReferenceGuide/avg/exampleB.csv"
USING Outputters.Csv();
```

**C.    Average values with OVER()**  
The [OVER](over-expression-u-sql.md) clause in the following query is empty which defines the "window" to include all rows. The query determines the average salary over the window - all employees.
```sql
@result =
    SELECT EmpName,
           AVG(Salary) OVER() AS AverageSalaryAllDepts
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/avg/exampleC.csv"
USING Outputters.Csv();
```

**D.    Average values over a defined window using OVER()**  
The [OVER](over-expression-u-sql.md) clause in the following query is `DeptName`.  The query returns `EmpName`, `DeptName`, and the average salary over the window - `DeptName`.
```sql
@result =
    SELECT EmpName,
           DeptName,
           AVG(Salary) OVER(PARTITION BY DeptName) AS AverageSalaryByDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/avg/exampleD.csv"
USING Outputters.Csv();
```

**E.    Average values over a defined window using OVER(), additional example**  
The [OVER](over-expression-u-sql.md) clause in the following query is `DeptName`.  The query returns all records, as well as the average salary for each `DeptName` and each employee's salary share of his/her department's average share.
```sql
@result =
    SELECT *,
           AVG(Salary) OVER(PARTITION BY DeptName) AS AverageSalaryByDept,
           ((decimal) Salary / AVG(Salary) OVER(PARTITION BY DeptName)) * 100 AS ShareOfAverageSalaryByDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/avg/exampleE.csv"
USING Outputters.Csv();
```

### See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
