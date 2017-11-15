---
title: "SUM (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 39f0b7a8-d3cd-4511-a124-e89ca12008ee
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# SUM (U-SQL)
The SUM aggregator returns the sum of all the values in the group. The input values have to be of a numeric type or an error is raised. Null values are ignored. 

The identity value is null. 

<table><th align="left">Syntax</th><tr><td><pre>
SUM_Expression :=                                                                                        
     'SUM' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**    
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation.  

* <a name="exp"></a>**`expression`**     
The C# expression (including column references) that gets aggregated. Its type has to be a numeric type or an error is raised. 

### Return Type 
The return type is determined by the type of the evaluated result of the expression as follows: 

|Expression type|Return type|Comment| 
|--|--|--|
|Integral types (short, int, uint, etc) implicitly castable to long and long?| long?|To be aligned with SQL semantics.|  
|ulong, ulong?|double?|Returns double to be able to handle large values.| 
|decimal, decimal?|decimal?||
|float, float?, double, double?|double?|| 

### Usage in Windowing Expression 
This aggregator can be used in a [windowing expression](../u-sql/over-expression-u-sql.md) without any additional restrictions. 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  
```
@employees = 
    SELECT * FROM ( VALUES
        (1, "Noah",   "Engineering", 100, 10000),
        (2, "Sophia", "Engineering", 100, 20000),
        (3, "Liam",   "Engineering", 100, 30000),
        (4, "Emma",   "HR",          200, 10000),
        (5, "Jacob",  "HR",          200, 10000),
        (6, "Olivia", "HR",          200, 10000),
        (7, "Mason",  "Executive",   300, 50000),
        (8, "Ava",    "Marketing",   400, 15000),
        (9, "Ethan",  "Marketing",   400, 10000) )
    AS T(EmpID, EmpName, DeptName, DeptID, Salary);
```

**A.  Sum of all values(`Salary`)**  
The following query: 1) calculates the total salary for all employees, and 2) calculates the total salary from all DISTINCT salary values.
```
@result =
    SELECT SUM(Salary) AS TotalSalary,
           SUM(DISTINCT Salary) AS TotalDistinctSalary
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/sum/exampleA.csv"
USING Outputters.Csv();
```

**B.    Sum of values per group**  
The following query calculates the total salary for each department with the [GROUP BY](../u-sql/group-by-and-having-clauses-u-sql.md) clause.
```
@result =
    SELECT DeptName,
           SUM(Salary) AS SalaryByDept
    FROM @employees
    GROUP BY DeptName;

OUTPUT @result
TO "/Output/ReferenceGuide/sum/exampleB.csv"
USING Outputters.Csv();
```

**C.    Sum of values with OVER()**  
The [OVER](../u-sql/over-expression-u-sql.md) clause in the following query is empty which defines the "window" to include all rows. The query calculates the total salary over the window - all employees.
```
@result =
    SELECT EmpName,
           SUM(Salary) OVER() AS SalaryAllDepts
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/sum/exampleC.csv"
USING Outputters.Csv();
```

**D.    Sum of values over a defined window using OVER()**  
The [OVER](../u-sql/over-expression-u-sql.md) clause in the following query is `DeptName`.  The query returns `EmpName`, `DeptName`, and the total salary over the window - `DeptName`.
```
@result =
    SELECT EmpName,
           DeptName,
           SUM(Salary) OVER(PARTITION BY DeptName) AS TotalSalaryByDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/sum/exampleD.csv"
USING Outputters.Csv();
```

**E.    Sum of values over a defined window using OVER(), additional example.**  
The [OVER](../u-sql/over-expression-u-sql.md) clause in the following query is `DeptName`.  The query returns all records, as well as the total salary for each `DeptName` and each employee's salary share of his/her total department's share.
```
@result =
    SELECT *,
           SUM(Salary) OVER(PARTITION BY DeptName) AS TotalSalaryByDept,
           ((decimal) Salary / SUM(Salary) OVER(PARTITION BY DeptName)) * 100 AS ShareOfTotalSalaryByDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/sum/exampleE.csv"
USING Outputters.Csv();
```

### See Also 
* [Aggregate Functions (U-SQL)](../u-sql/aggregate-functions-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](../u-sql/group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](../u-sql/over-expression-u-sql.md) 
