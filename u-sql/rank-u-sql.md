---
title: "RANK (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 1a070ccb-2e33-44ea-8b20-f5cabbdb8149
caps.latest.revision: 7
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# RANK (U-SQL)
The RANK ranking function returns the rank of each row within the window. The rank of a row is one plus the number of ranks that come before the row in question.  

If two or more rows tie for a rank, each tied rows receives the same rank and the next highest row will receive the rank as if the previous rows were not tied. For example, if the three top salespeople have the same SalesYTD value, they are all ranked one. The salesperson with the next highest SalesYTD is ranked number four, because there are three rows that are ranked higher. Therefore, the RANK function does not always return consecutive integers.  

The sort order that is used for the whole query determines the order in which the rows appear in a result set. 

RANK can only be used in the context of a [windowing expression](over-expression-u-sql.md). 

<table><th align="left">Syntax</th><tr><td><pre>
RANK_Expression :=                                                                                       
     'RANK' '(' ')'.
</pre></td></tr></table>

### Return Type 
The return type is [long?](numeric-types-and-literals.md). 

### Usage in Windowing Expression 
This ranking function can be used in a [windowing expression](over-expression-u-sql.md) with the following restrictions: 

* The [ORDER BY](over-expression-u-sql.md#OBC) clause in the [OVER](over-expression-u-sql.md) operator is required. 
* The [ROWS](over-expression-u-sql.md#row_cla) clause in the [OVER](over-expression-u-sql.md) operator is not allowed. 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  

   ```sql
    @employees = 
        SELECT * FROM 
            ( VALUES
            (1, "Noah",   "Engineering", 100, 10000),
            (2, "Sophia", "Engineering", 100, 15000),
            (3, "Liam",   "Engineering", 100, 30000),
            (4, "Amy",    "Engineering", 100, 35000),
            (5, "Justin", "Engineering", 100, 15000),
            (6, "Emma",   "HR",          200, 8000),
            (7, "Jacob",  "HR",          200, 8000),
            (8, "Olivia", "HR",          200, 8000),
            (9, "Mason",  "Executive",   300, 50000),
            (10, "Ava",   "Marketing",   400, 15000),
            (11, "Ethan", "Marketing",   400, 9000) 
            ) AS T(EmpID, EmpName, DeptName, DeptID, Salary);
   ```

**A.  Ranking all rows in a result set**   
The following example returns all employees ranked by his/her salary. Because a [PARTITION BY](over-expression-u-sql.md#OPBC) clause was not specified, the `RANK` function was applied to all rows in the result set.
```sql
@result =
    SELECT *,
           RANK() OVER(ORDER BY Salary DESC) AS SalaryRank
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/Ranking/rank/exampleA.csv"
USING Outputters.Csv();
```

**B.  Ranking rows within a partition**   
The following example ranks the salaries within each department. The result set is partitioned by `DeptID` and logically ordered by `Salary`.
```sql
@result =
    SELECT *,
           RANK() OVER(PARTITION BY DeptID ORDER BY Salary DESC) AS SalaryRankByDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/Ranking/rank/exampleB.csv"
USING Outputters.Csv();
```

### See Also 
* [DENSE_RANK (U-SQL)](dense-rank-u-sql.md)
* [Ranking Functions (U-SQL)](ranking-functions-u-sql.md)  
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
