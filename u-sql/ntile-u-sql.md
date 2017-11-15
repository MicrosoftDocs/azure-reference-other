---
title: "NTILE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 506a52f9-8e11-480f-8e71-5f594d74d601
caps.latest.revision: 9
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# NTILE (U-SQL)
The NTILE ranking function returns the number of the group to which the row belongs from among the groups that the windowing function has distributed the rows using an ordered partition. The groups are numbered, starting at one.  

If the number of rows in a partition is not divisible by the provided integer, it will cause groups of two sizes that differ by one member. Larger groups come before smaller groups in the order specified by the [OVER](over-expression-u-sql.md) clause. For example, if the total number of rows is 53 and the number of groups is five, the first three groups will have 11 rows and the two remaining groups will have 10 rows each. If on the other hand the total number of rows is divisible by the number of groups, the rows will be evenly distributed among the groups. For example, if the total number of rows is 50, and there are five groups, each bucket will contain 10 rows. 

NTILE can only be used in the context of a [windowing expression](over-expression-u-sql.md). 

<table><th align="left">Syntax</th><tr><td><pre>
NTILE_Expression :=                                                                                      
     'NTILE' '(' <a href="#grp_cnt">Group_Count</a> ')'.<br />
<a href="#grp_cnt">Group_Count</a> := 
     <a href="numeric-types-and-literals.md">long_literal</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="grp_cnt"></a>**`Group_Count`**    
Is a positive, nonnull constant of type [long](numeric-types-and-literals.md) that specifies the number of groups into which each partition must be divided. 
 
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
```
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

**A.  Dividing rows into groups**   
The following example divides rows into four groups of employees.
```
@result =
    SELECT *,
           NTILE(4) OVER() AS Quartile2
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/Ranking/ntile/exampleA.csv"
USING Outputters.Csv();
```

**B.  Dividing rows into groups and using ORDER BY**   
The following example divides rows into four groups of employees based on his\her `Salary`.
```
@result =
    SELECT *,
           NTILE(4) OVER(ORDER BY Salary DESC) AS QuartileBySalary
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/Ranking/ntile/exampleB.csv"
// ORDER BY Salary DESC
USING Outputters.Csv();
```

**C.  Dividing the result set by using PARTITION BY**   
The rows are first partitioned by `DeptID` and then divided into two groups within each `DeptID`.
```
@result =
    SELECT *,
           NTILE(2) OVER(PARTITION BY DeptID) AS Median
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/Ranking/ntile/exampleC.csv"
USING Outputters.Csv();
```

**D.  Dividing the result set by using PARTITION BY and ORDER BY**   
The rows are first partitioned by `DeptID` and then divided into two groups within each `DeptID` based on his\her `Salary`.
```
@result =
    SELECT *,
           NTILE(2) OVER(PARTITION BY DeptID ORDER BY Salary DESC) AS MedianBySalary
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/Ranking/ntile/exampleD.csv"
USING Outputters.Csv();
```

### See Also 
* [Ranking Functions (U-SQL)](ranking-functions-u-sql.md)  
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 


