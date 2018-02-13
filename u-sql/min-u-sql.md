---
title: "MIN (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b6e11d21-984b-4820-ae57-ea22115e8287
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# MIN (U-SQL)
The MIN aggregator choses the smallest value in the group or null if the expression returns only nulls in the group. The values have to be comparable. For string types, it uses a culture-invariant UTF-8 byte ordering. 

The identity value is null. 

<table><th align="left">Syntax</th><tr><td><pre>
MIN_Expression :=                                                                                        
     'MIN' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**     
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation. DISTINCT is not meaningful with MIN and is available for ISO compatibility only. 

* <a name="exp"></a>**`expression`**      
The C# expression (including column references) that gets aggregated. Its result type has to be comparable. 

### Return Type 
The nullable type of the input. 

### Usage in Windowing Expression 
This aggregator can be used in a [windowing expression](over-expression-u-sql.md) without any additional restrictions. 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  
    ```sql
    @employees = 
        SELECT * FROM 
            ( VALUES
            (1, "Noah",   "Engineering", 100, 10000),
            (2, "Sophia", "Engineering", 100, 20000),
            (3, "Liam",   "Engineering", 100, 30000),
            (4, "Emma",   "HR",          200, 8000),
            (5, "Jacob",  "HR",          200, 8000),
            (6, "Olivia", "HR",          200, 8000),
            (7, "Mason",  "Executive",   300, 50000),
            (8, "Ava",    "Marketing",   400, 15000),
            (9, "Ethan",  "Marketing",   400, 9000) 
            ) AS T(EmpID, EmpName, DeptName, DeptID, Salary);
    ```

**A.    Lowest value(`Salary`)**   
The following query determines the single lowest salary.
```sql
@result =
    SELECT MIN(Salary) AS LowestSalary
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/min/exampleA.csv"
USING Outputters.Csv();
```

**B.    Lowest values per group**    
The following query determines the lowest salary for each department with the [GROUP BY](group-by-and-having-clauses-u-sql.md) clause.
```sql
@result =
    SELECT DeptName,
           MIN(Salary) AS LowestSalaryByDept
    FROM @employees
    GROUP BY DeptName;

OUTPUT @result
TO "/Output/ReferenceGuide/min/exampleB.csv"
USING Outputters.Csv();
```
  
**C.    Lowest values with OVER()**   
The [OVER](over-expression-u-sql.md) clause in the following query is empty which defines the "window" to include all rows.  The query determines the lowest salary over the window - all employees.
```sql
@result =
    SELECT EmpName,
           MIN(Salary) OVER() AS LowestSalaryAllDepts
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/min/exampleC.csv"
USING Outputters.Csv();
```

**D.    Lowest values over a defined window using OVER()**    
The [OVER](over-expression-u-sql.md) clause in the following query is `DeptName`.  The query returns `EmpName`, `DeptName`, and the lowest salary over the window - `DeptName`.
```sql
@result =
    SELECT EmpName,
           DeptName,
           MIN(Salary) OVER(PARTITION BY DeptName) AS LowestSalaryByDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/min/exampleD.csv"
USING Outputters.Csv();
```

**E.    Lowest values over a defined window using OVER(), additional example**   
The [OVER](over-expression-u-sql.md) clause in the following query is `DeptName`.  The query returns all records, as well as the lowest salary for each department and each employee's salary share of his/her department's lowest share.
```sql
@result =
    SELECT *,
           MIN(Salary) OVER(PARTITION BY DeptName) AS LowestSalaryByDept,
           ((decimal) Salary / MIN(Salary) OVER(PARTITION BY DeptName)) * 100 AS ShareOfLowestSalaryByDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/min/exampleE.csv"
USING Outputters.Csv();
```

### See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
