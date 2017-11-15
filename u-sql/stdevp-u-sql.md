---
title: "STDEVP (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 5a492d5b-08a8-4e59-8355-a386be47c26f
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# STDEVP (U-SQL)
The STDEVP aggregator returns the statistical standard deviation for the population for all nonnull values in the group or returns null if all the input values are null. The values have to be numeric or an error is raised. 

The identity value is null. 

<table><th align="left">Syntax</th><tr><td><pre>
STDEVP_Expression :=                                                                                     
     'STDEVP' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**    
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation.  

* <a name="exp"></a>**`expression`**    
The C# expression (including column references) that gets aggregated. The type of the expression has to be a numeric type or an error is raised. 

### Return Type 
The return type is [double?](../u-sql/numeric-types-and-literals.md). 

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
        (4, "Emma",   "HR",          200, 8000),
        (5, "Jacob",  "HR",          200, 8000),
        (6, "Olivia", "HR",          200, 8000),
        (7, "Mason",  "Executive",   300, 50000),
        (8, "Ava",    "Marketing",   400, 15000),
        (9, "Ethan",  "Marketing",   400, 9000) 
        ) AS T(EmpID, EmpName, DeptName, DeptID, Salary);
```

**A.    Using STDEVP**   
The following query returns the standard deviation for the population of all: 1) salary values, and 2) distinct salary values.
```
@result =
    SELECT STDEVP(Salary) AS STDEVP_AllSalaries,
           STDEVP(DISTINCT Salary) AS STDEVP_DistinctSalaries
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/stdevp/exampleA.csv"
USING Outputters.Csv();
```

**B.    STDEVP per group**   
The following query determines the standard deviation for the salary population for each department with the [GROUP BY](../u-sql/group-by-and-having-clauses-u-sql.md) clause.
```
@result =
    SELECT DeptName,
           STDEVP(Salary) AS STDEVPSalaryByDept
    FROM @employees
    GROUP BY DeptName;

OUTPUT @result
TO "/Output/ReferenceGuide/stdevp/exampleB.csv"
USING Outputters.Csv();
```

**C.    STDEVP with OVER()**   
The [OVER](../u-sql/over-expression-u-sql.md) clause in the following query is empty which defines the "window" to include all rows.  The query determines the standard deviation for the salary population over the window - all employees.
```
@result =
    SELECT EmpName,
           STDEVP(Salary) OVER() AS STDEV_AllSalaries
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/stdevp/exampleC.csv"
USING Outputters.Csv();
```

**D.    STDEVP over a defined window using OVER()**   
The [OVER](../u-sql/over-expression-u-sql.md) clause in the following query is `DeptName`.  The query returns `EmpName`, `DeptName`, `Salary`, and the standard deviation for the salary population over the window - `DeptName`.
```
@result =
    SELECT EmpName,
           DeptName,
           Salary,
           STDEVP(Salary) OVER(PARTITION BY DeptName) AS STDEVPSalaryByDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/stdevp/exampleD.csv"
USING Outputters.Csv();
```
 
### See Also 
* [Aggregate Functions (U-SQL)](../u-sql/aggregate-functions-u-sql.md)  
* [STDEV (U-SQL) ](../u-sql/stdev-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](../u-sql/group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](../u-sql/over-expression-u-sql.md) 
