---
title: "CUME_DIST (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ab535e58-e844-4cc1-8b04-0a0a5ad2e4d2
caps.latest.revision: 9
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CUME_DIST (U-SQL)
The CUME_DIST analytic function calculates the cumulative distribution of a value in a group of values. That is, CUME_DIST computes the relative position of a specified value in a group of values. For a row r, assuming ascending ordering, the CUME_DIST of r is the number of rows with values lower than or equal to the value of r, divided by the number of rows evaluated in the group. Thus, the range of values returned by CUME_DIST is greater than 0 and less than or equal to 1. Tie values always evaluate to the same cumulative distribution value. NULL values are included by default and are treated as the highest possible values. 

CUME_DIST is similar to the [PERCENT_RANK](../USQL/percent-rank-u-sql.md) function. 

CUME_DIST can only be used in the context of a [windowing expression](../USQL/over-expression-u-sql.md). 

<table><th align="left">Syntax</th><tr><td><pre>
CUME_DIST_Expression :=                                                                                  
    'CUME_DIST' '(' ')'.
</pre></td></tr></table>

### Return Type 
The return type is [double?](../USQL/numeric-types-and-literals.md). 

### Usage in Windowing Expression 
This analytic function can be used in a [windowing expression](../USQL/over-expression-u-sql.md) with the following restrictions: 

* The [ROWS](../USQL/over-expression-u-sql.md#row_cla) clause in the [OVER](../USQL/over-expression-u-sql.md) operator is not allowed. 

### Example
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The example below is based on the dataset defined below.  Ensure you create and populate the table in a separate window before executing the example.
```
CREATE DATABASE IF NOT EXISTS TestReferenceDB;
USE DATABASE TestReferenceDB; 

DROP TABLE IF EXISTS dbo.Employees;
CREATE TABLE dbo.Employees
(
    EmpID int,
    EmpName string,
    DeptName string,
    DeptID int,
    Salary int?,
    INDEX cl_idx CLUSTERED(EmpID ASC) PARTITIONED BY HASH(EmpID)
);

INSERT INTO dbo.Employees
(EmpID, EmpName, DeptName, DeptID, Salary)
VALUES
(1, "Noah",   "Engineering", 100, (int?)10000),
(2, "Sophia", "Engineering", 100, (int?)20000),
(3, "Liam",   "Engineering", 100, (int?)30000),
(4, "Amy",    "Engineering", 100, (int?)35000),
(5, "Emma",   "HR",          200, (int?)8000),
(6, "Jacob",  "HR",          200, (int?)8000),
(7, "Olivia", "HR",          200, (int?)8000),
(8, "Mason",  "Executive",   300, (int?)50000),
(9, "Ava",    "Marketing",   400, (int?)15000),
(10, "Ethan", "Marketing",  400, (int?)9000);

// Create a NULL DeptName
INSERT INTO dbo.Employees
(EmpID, EmpName, DeptID, Salary)
VALUES
(11, "David", 800, (int?)100);

// Create a NULL Salary
INSERT INTO dbo.Employees
(EmpID, EmpName, DeptName, DeptID)
VALUES
(12, "Andrew", "Engineering", 100);
```

**Using CUME_DIST**    
The following example uses the CUME_DIST function to compute the salary percentile for each employee within a given department. The value returned by the CUME_DIST function represents the percent of employees that have a salary less than or equal to the current employee in the same department. The [PARTITION BY](../USQL/over-expression-u-sql.md#OPBC) clause is specified to partition the rows in the result set by department. The [ORDER BY](../USQL/over-expression-u-sql.md#OBC) clause in the OVER clause logically orders the rows in each partition. 
```
@result =
    SELECT *,
         CUME_DIST() OVER(PARTITION BY DeptID ORDER BY Salary) AS CumeDistSalary
    FROM TestReferenceDB.dbo.Employees;

OUTPUT @result
TO "/Output/ReferenceGuide/cume_dist/example.csv"
USING Outputters.Csv();
```

### See Also 
* [Analytic Functions (U-SQL)](../USQL/analytic-functions-u-sql.md)  
* [PERCENT_RANK (U-SQL)](../USQL/percent-rank-u-sql.md) 
* [OVER Expression (U-SQL)](../USQL/over-expression-u-sql.md) 
