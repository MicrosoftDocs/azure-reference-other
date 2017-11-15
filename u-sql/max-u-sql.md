---
title: "MAX (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 3e0f1b7d-66e5-4e5f-bbd8-6e4de221eda5
caps.latest.revision: 7
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# MAX (U-SQL)
The MAX aggregator choses the largest value in the group or null if the expression returns only nulls in the group. The values have to be comparable. For string types, it uses a culture-invariant UTF-8 byte ordering. 

The identity value is null. 

<table><th align="left">Syntax</th><tr><td><pre>
MAX_Expression :=                                                                                        
     'MAX' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**     
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation. DISTINCT is not meaningful with MAX and is available for ISO compatibility only. 

* <a name="exp"></a>**`expression`**    
The C# expression (including column references) that gets aggregated. Its result type has to be comparable. 

### Return Type 
The nullable type of the input. 

### Usage in Windowing Expression 
This aggregator can be used in a [windowing expression](../u-sql/over-expression-u-sql.md) without any additional restrictions. 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  
```
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

**A.    Highest value(`Salary`)**  
The following query determines the single highest salary.
```
@result =
    SELECT MAX(Salary) AS HighestSalary
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/max/exampleA.csv"
USING Outputters.Csv();
```

**B.    Highest values per group**  
The following query determines the highest salary for each department with the [GROUP BY](../u-sql/group-by-and-having-clauses-u-sql.md) clause.
```
@result =
    SELECT DeptName,
           MAX(Salary) AS HighestSalaryByDept
    FROM @employees
    GROUP BY DeptName;

OUTPUT @result
TO "/Output/ReferenceGuide/max/exampleB.csv"
USING Outputters.Csv();
```

**C.    Highest values with OVER()**   
The [OVER](../u-sql/over-expression-u-sql.md) clause in the following query is empty which defines the "window" to include all rows. The query determines the highest salary over the window - all employees.
```
@result =
    SELECT EmpName,
           MAX(Salary) OVER() AS HighestSalaryAllDepts
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/max/exampleC.csv"
USING Outputters.Csv();
```

**D.    Highest values over a defined window using OVER()**   
The [OVER](../u-sql/over-expression-u-sql.md) clause in the following query is `DeptName`. The query returns `EmpName`, `DeptName`, and the highest salary over the window - `DeptName`.
```
@result =
    SELECT EmpName,
           DeptName,
           MAX(Salary) OVER(PARTITION BY DeptName) AS HighestSalaryByDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/max/exampleD.csv"
USING Outputters.Csv();
```

**E.    Highest values over a defined window using OVER(), additional example.**   
The [OVER](../u-sql/over-expression-u-sql.md) clause in the following query is `DeptName`.  The query returns all records, as well as the highest salary for each department and each employee's salary share of his/her department's highest share.
```
@result =
    SELECT *,
           MAX(Salary) OVER(PARTITION BY DeptName) AS HighestSalaryByDept,
           ((decimal) Salary / MAX(Salary) OVER(PARTITION BY DeptName)) * 100 AS ShareOfHighestSalaryByDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/max/exampleE.csv"
USING Outputters.Csv();
```

### See Also 
* [Aggregate Functions (U-SQL)](../u-sql/aggregate-functions-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](../u-sql/group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](../u-sql/over-expression-u-sql.md) 
