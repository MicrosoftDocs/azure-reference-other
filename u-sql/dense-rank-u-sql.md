---
title: "DENSE_RANK (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 756b74bc-d005-4499-9656-f1071db579b7
caps.latest.revision: 8
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# DENSE_RANK (U-SQL)
The DENSE_RANK ranking function returns the rank of rows within the partition of a window, without any gaps in the ranking. The rank of a row is one plus the number of distinct ranks that come before the row in question. 

DENSE_RANK can only be used in the context of a [windowing expression](over-expression-u-sql.md). 
  
<table><th align="left">Syntax</th><tr><td><pre>
DENSE_RANK_Expression :=                                                                                 
    'DENSE_RANK' '(' ')'.
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

**A.    Ranking all rows in a result set**   
The following example returns all records ranked by salary.  Because a [PARTITION BY](over-expression-u-sql.md#OPBC) clause was not specified, the `DENSE_RANK` function was applied to all rows in the result set.
```sql
@result =
    SELECT *,
           DENSE_RANK() OVER(ORDER BY Salary DESC) AS DenseRankAll
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/Ranking/dense_rank/exampleA.csv"
ORDER BY Salary DESC
USING Outputters.Csv();
```

**B.    Ranking rows within a partition**   
The following example ranks the salary per department.  The result set is partitioned by `DeptID` and logically ordered by `Salary`.
```sql
@result =
    SELECT *,
           DENSE_RANK() OVER(PARTITION BY DeptID ORDER BY Salary DESC) AS DenseRankByDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/Ranking/dense_rank/exampleB.csv"
ORDER BY DeptID ASC,
         Salary DESC
USING Outputters.Csv();
```

### See Also 
* [Ranking Functions (U-SQL)](ranking-functions-u-sql.md)  
* [OVER Expression (U-SQL)](over-expression-u-sql.md)  
