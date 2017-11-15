---
title: "FIRST_VALUE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 2f5cd094-2634-4430-9e95-e87f43d0a32c
caps.latest.revision: 7
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# FIRST_VALUE (U-SQL)
The FIRST_VALUE analytic function returns the first value in an ordered set of values provided by the windowing expression. 

FIRST_VALUE can only be used in the context of a [windowing expression](../USQL/over-expression-u-sql.md). 

<table><th align="left">Syntax</th><tr><td><pre>
FIRST_VALUE_Expression :=                                                                                
    'FIRST_VALUE' '(' <a href="#exp">expression</a> ')'.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="exp"></a>**`expression`**     
The expression for which the first value gets calculated for the window.. 

### Return Type 
The nullable type of the input. 

### Usage in Windowing Expression 
This analytic function can be used in a [windowing expression](../USQL/over-expression-u-sql.md) with the following restrictions: 
* The [ORDER BY](../USQL/over-expression-u-sql.md#OBC) clause in the [OVER](../USQL/over-expression-u-sql.md) operator is required. 

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
        (4, "Amy",    "Engineering", 100, 35000),
        (5, "Emma",   "HR",          200, 8000),
        (6, "Jacob",  "HR",          200, 8000),
        (7, "Olivia", "HR",          200, 8000),
        (8, "Mason",  "Executive",   300, 50000),
        (9, "Ava",    "Marketing",   400, 15000),
        (10, "Ethan", "Marketing",   400, 9000) 
        ) AS T(EmpID, EmpName, DeptName, DeptID, Salary);
```

**A.    Using FIRST_VALUE**   
The following example uses FIRST_VALUE to return the name of the employee that is the highest paid for a given department.
```
@result =
    SELECT EmpName,
           Salary,
           FIRST_VALUE(EmpName) OVER(ORDER BY Salary DESC) AS HighestPaidEmployee
    FROM @employees
    WHERE DeptID == 100;
   
OUTPUT @result
TO "/Output/ReferenceGuide/first_value/exampleA.csv"
USING Outputters.Csv();
```

**B.    Using FIRST_VALUE over partitions**   
The following example uses FIRST_VALUE to return the highest paid employee compared to other employees within the same department.  The [PARTITION BY](../USQL/over-expression-u-sql.md#OPBC) clause partitions the employees by department and the FIRST_VALUE function is applied to each partition independently.  The [ORDER BY](../USQL/over-expression-u-sql.md#OBC) clause specified in the [OVER](../USQL/over-expression-u-sql.md) clause determines the logical order in which the FIRST_VALUE function is applied to the rows in each partition.
```
@result =
    SELECT DeptName,
           EmpName,
           Salary,
           FIRST_VALUE(EmpName) OVER(PARTITION BY DeptID ORDER BY Salary DESC) AS HighestPaidEmployeePerDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/first_value/exampleB.csv"
USING Outputters.Csv();
```

### See Also 
* [Analytic Functions (U-SQL)](../USQL/analytic-functions-u-sql.md)  
* [OVER Expression (U-SQL)](../USQL/over-expression-u-sql.md) 


