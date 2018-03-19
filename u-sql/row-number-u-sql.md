---
title: "ROW_NUMBER (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a7048e15-190c-4c4e-8693-bf1217b171ae
caps.latest.revision: 13
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# ROW_NUMBER (U-SQL)
The ROW_NUMBER ranking function returns the sequential number of a row within a window, starting at 1 for the first row in each window. 

There is no guarantee that the rows returned by a query using ROW_NUMBER will be deterministically ordered exactly the same with each execution unless all of the following conditions are true. 

1. Values of the partitioned column are unique. 

2. Values of the [ORDER BY](order-by-and-offset-fetch-clause-u-sql.md) columns are unique. 

3. Combinations of values of the partition column and [ORDER BY](order-by-and-offset-fetch-clause-u-sql.md) columns are unique. 

ROW_NUMBER can only be used in the context of a [windowing expression](over-expression-u-sql.md). 
    
<table><th align="left">Syntax</th><tr><td><pre>
ROW_NUMBER_Expression :=                                                                                 
      'ROW_NUMBER' '(' ')'.  
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

**A.    Basic Syntax**   
The following example calculates a row number for each employee based on his\her `Salary`.
```sql
@result =
    SELECT ROW_NUMBER() OVER (ORDER BY Salary DESC) AS RowNumber,
    EmpName, DeptName, Salary
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/Ranking/row_number/exampleA.csv"
// ORDER BY Salary DESC
USING Outputters.Csv();
```

**B.    Dividing the result set using PARTITION BY**   
The rows are first partitioned by `DeptID`. The [ORDER BY](over-expression-u-sql.md#OBC) clause specified in the [OVER](over-expression-u-sql.md) clause orders the rows in each partition by the column `Salary`.
```sql
@result =
    SELECT ROW_NUMBER() OVER(PARTITION BY DeptID ORDER BY Salary DESC) AS RowNumberByDept,
           EmpName, DeptName, Salary
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/Ranking/row_number/exampleB.csv"
USING Outputters.Csv();
```

### See Also 
* [Ranking Functions (U-SQL)](ranking-functions-u-sql.md)  
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 


















