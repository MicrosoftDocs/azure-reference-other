---
title: "PERCENT_RANK (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e67015f4-620a-4b3c-979e-77196bb8412b
caps.latest.revision: 8
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# PERCENT_RANK (U-SQL)
The `PERCENT_RANK` analytic function calculates the relative rank of a row within a group of rows specified by the [windowing expression](over-expression-u-sql.md).  

The range of values returned by `PERCENT_RANK` is greater than or equal to 0 and less than or equal to 1. The first row in any set has a `PERCENT_RANK` of 0. NULL values are included by default and are treated as the highest possible values. 

Use `PERCENT_RANK` to evaluate the relative standing of a value within the window.  

`PERCENT_RANK` is similar to the [CUME_DIST](cume-dist-u-sql.md) function. 

`PERCENT_RANK` can only be used in the context of the [OVER](over-expression-u-sql.md) expression. 

## Syntax
<pre>
PERCENT_RANK_Expression := 
    'PERCENT_RANK' '(' ')'.
</pre>

## Return Type 
The return type is [double?](numeric-types-and-literals.md). 

## Usage in Windowing Expression  
This analytic function can be used in a [windowing expression](over-expression-u-sql.md) with the following restrictions: 
* The [ROWS](over-expression-u-sql.md#row_cla) clause in the [OVER](over-expression-u-sql.md) operator is not allowed. 

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The example(s) below are based on the dataset(s) defined below.  Ensure your execution includes the rowset variable(s).

**Dataset**   
```sql
@employees = 
    SELECT * FROM 
        ( VALUES
        (1, "Jennie", 100, (int?)34000, new DateTime(2000,02,12)),
        (2, "Noah",   100, (int?)10000, new DateTime(2012,05,31)),
        (3, "Sophia", 100, (int?)15000, new DateTime(2012,03,19)),
        (4, "Liam",   100, (int?)30000, new DateTime(2014,09,14)),
        (5, "Amy",    100, (int?)35000, new DateTime(1999,02,27)),
        (6, "Justin", 100, (int?)15000, new DateTime(2015,01,12)),
        (7, "Emma",   200, (int?)8000,  new DateTime(2014,03,08)),
        (8, "Jacob",  200, (int?)8000,  new DateTime(2014,09,02)),
        (9, "Olivia", 200, (int?)8000,  new DateTime(2013,12,11)),
        (10, "Mason", 300, (int?)50000, new DateTime(2016,01,01)),
        (11, "Ava",   300, (int?)15000, new DateTime(2014,09,14)),
        (12, "Ethan", 300, (int?)9000,  new DateTime(2015,08,22)),
        (13, "David", 300, (int?)100,   new DateTime(2016,11,01))
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate);
```

**Using PERCENT_RANK - undefined window**    
The `OVER` expression in the following query is empty which defines the "window" to include all rows.   
The query calculates the relative rank of an employee's salary over the window - all employees.
```sql
@result =
    SELECT EmpName, DeptID, Salary,
           PERCENT_RANK() OVER(ORDER BY Salary) AS PercentRankSalary_AllEmployees,
           CUME_DIST() OVER(ORDER BY Salary) AS CumeDistSalary_AllEmployees
    FROM @employees;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/percent_rank/example1.csv"
USING Outputters.Csv(outputHeader: true);
```
<br />


**Using PERCENT_RANK - defined window**     
The `OVER` expressions in the following query defines the window by partitioning the rowsets on DeptID.
The query calculates the relative rank of an employee's salary over the window - each department. 
```sql
@result =
    SELECT EmpName, DeptID, Salary,
           PERCENT_RANK() OVER(PARTITION BY DeptID ORDER BY Salary) AS PercentRankSalary_ByDeptID,
           CUME_DIST() OVER(PARTITION BY DeptID ORDER BY Salary) AS CumeDistSalary_ByDeptID
    FROM @employees;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/percent_rank/example2.csv"
USING Outputters.Csv(outputHeader: true);
```
<br />

## See Also 
* [Analytic Functions (U-SQL)](analytic-functions-u-sql.md)   
* [CUME_DIST (U-SQL)](cume-dist-u-sql.md)  
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 



