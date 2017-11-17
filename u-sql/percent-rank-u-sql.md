---
title: "PERCENT_RANK (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e67015f4-620a-4b3c-979e-77196bb8412b
caps.latest.revision: 8
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# PERCENT_RANK (U-SQL)
The PERCENT_RANK analytic function calculates the relative rank of a row within a group of rows specified by the [windowing expression](over-expression-u-sql.md).  

The range of values returned by PERCENT_RANK is greater than or equal to 0 and less than or equal to 1. The first row in any set has a PERCENT_RANK of 0. NULL values are included by default and are treated as the highest possible values. 

Use PERCENT_RANK to evaluate the relative standing of a value within the window.  

PERCENT_RANK is similar to the [CUME_DIST](cume-dist-u-sql.md) function. 

PERCENT_RANK can only be used in the context of the [OVER](over-expression-u-sql.md) expression. 

<table><th align="left">Syntax</th><tr><td><pre>
PERCENT_RANK_Expression :=                                                                               
     'PERCENT_RANK' '(' ')'.
</pre></td></tr></table>

### Return Type 
The return type is [double?](numeric-types-and-literals.md). 

### Usage in Windowing Expression  
This analytic function can be used in a [windowing expression](over-expression-u-sql.md) with the following restrictions: 
* The [ROWS](over-expression-u-sql.md#row_cla) clause in the [OVER](over-expression-u-sql.md) operator is not allowed. 

### Example
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The example below is based on the dataset defined below.  Ensure your execution includes the rowset variable.
```
@employees = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",   "Engineering", 100, 10000),
        (2, "Sophia", "Engineering", 100, 20000),
        (3, "Liam",   "Engineering", 100, 30000),
        (4, "Amy",    "Engineering", 100, 35000),
        (5, "Emma",   "HR",          200, 8000),
        (6, "Jacob",  "HR",          200, 8000),
        (7, "Olivia", "HR",          200, 8000),
        (8, "Mason",  "Executive",   300, 50000),
        (9, "Ava",    "Marketing",   400, 15000),
        (10, "Ethan", "Marketing",   400, 9000) 
        ) AS T(EmpID, EmpName, DeptName, DeptID, Salary);
```

**Using PERCENT_RANK**   
The `PERCENT_RANK` function computes the rank of the employee's salary within a department as a percentage.  The [PARTITION BY](over-expression-u-sql.md#OPBC) clause is specified to partition the rows in the result set by department.  The [ORDER BY](over-expression-u-sql.md#OBC) clause in the [OVER](over-expression-u-sql.md) clause orders the rows in each partition. 
```
@result =
    SELECT *,
           PERCENT_RANK() OVER(PARTITION BY DeptID ORDER BY Salary) AS PercentRank
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/percent_rank/example.csv"
USING Outputters.Csv();
```

### See Also 
* [Analytic Functions (U-SQL)](analytic-functions-u-sql.md)   
* [CUME_DIST (U-SQL)](cume-dist-u-sql.md)  
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 



