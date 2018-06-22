---
title: "CUME_DIST (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ab535e58-e844-4cc1-8b04-0a0a5ad2e4d2
caps.latest.revision: 9
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# CUME_DIST (U-SQL)
The CUME_DIST analytic function calculates the cumulative distribution of a value in a group of values. That is, CUME_DIST computes the relative position of a specified value in a group of values. For a row r, assuming ascending ordering, the CUME_DIST of r is the number of rows with values lower than or equal to the value of r, divided by the number of rows evaluated in the group. Thus, the range of values returned by CUME_DIST is greater than 0 and less than or equal to 1. Tie values always evaluate to the same cumulative distribution value. NULL values are included by default and are treated as the highest possible values. 

CUME_DIST is similar to the [PERCENT_RANK](percent-rank-u-sql.md) function. 

CUME_DIST can only be used in the context of a [windowing expression](over-expression-u-sql.md). 

## Syntax
<pre>
CUME_DIST_Expression := 
    'CUME_DIST' '(' ')'.
</pre>

## Return Type 
The return type is [double?](numeric-types-and-literals.md). 

## Usage in Windowing Expression 
This analytic function can be used in a [windowing expression](over-expression-u-sql.md) with the following restrictions: 

* The [ROWS](over-expression-u-sql.md#row_cla) clause in the [OVER](over-expression-u-sql.md) operator is not allowed. 

## Example
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
<br />


**Using CUME_DIST**  
The following example uses the `CUME_DIST` function to compute the salary percentile for each employee within a given department. 
The value returned by the `CUME_DIST` function represents the percent of employees that have a salary less than or equal to the current employee in the same department. 
The [PERCENT_RANK](percent-rank-u-sql.md) function computes the rank of the employee's salary within a department as a percentage. 
The [PARTITION BY](over-expression-u-sql.md#OPBC) clause is specified to partition the rows in the result set by department.
The [ORDER BY](over-expression-u-sql.md#OBC) clause in the [OVER](over-expression-u-sql.md) clause logically orders the rows in each partition. 
```sql
@result =
    SELECT  EmpName, DeptID, Salary,
            CUME_DIST() OVER (PARTITION BY DeptID ORDER BY Salary) AS CumeDistSalaryByDept,
            PERCENT_RANK() OVER(PARTITION BY DeptID ORDER BY Salary) AS PercentRankSalaryByDept
    FROM @employees;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/CUME_DIST/example1.csv"
USING Outputters.Csv(outputHeader: true);
```
<br />


**Additional Example**  
```sql
@result =
    SELECT  DeptID, EmpName, Salary,
            "Approximately " +
            Math.Truncate((double)CUME_DIST() OVER (PARTITION BY DeptID ORDER BY Salary) * 100).ToString() +
            " percent of the records in the defined window, partition, have a value less than or equal to " +
            Salary.ToString() AS CumeDistSalaryByDept
    FROM @employees;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/CUME_DIST/example2.csv"
USING Outputters.Csv(outputHeader: true);
```
<br />

## See Also 
* [Analytic Functions (U-SQL)](analytic-functions-u-sql.md)  
* [PERCENT_RANK (U-SQL)](percent-rank-u-sql.md) 
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
