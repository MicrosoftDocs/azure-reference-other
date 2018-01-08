---
title: "LAST_VALUE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: f356ebc7-24ea-449e-8d16-7f8867d89d79
caps.latest.revision: 8
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# LAST_VALUE (U-SQL)
The LAST_VALUE analytic function returns the last value in an ordered set of values provided by the [windowing expression](over-expression-u-sql.md). 

LAST_VALUE can only be used in the context of a [windowing expression](over-expression-u-sql.md). 

<table><th align="left">Syntax</th><tr><td><pre>
LAST_VALUE_Expression :=                                                                                 
     'LAST_VALUE' '(' <a href="#exp">expression</a> ')'.
</pre></td></tr></table>


### Semantics of Syntax Elements 
* <a name="exp"></a>**`expression`**   
The expression for which the last value gets calculated for the window.  

### Return Type 
The nullable type of the input. 

### Usage in Windowing Expression 
This analytic function can be used in a [windowing expression](over-expression-u-sql.md) with the following restrictions: 

* The [ORDER BY](over-expression-u-sql.md#OBC) clause in the [OVER](over-expression-u-sql.md) operator is required. 

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

**A.    Using LAST_VALUE**   
The following example uses `LAST_VALUE` to return the name of the employee that is the lowest paid for a given department.
```
@result =
    SELECT EmpName,
           Salary,
           LAST_VALUE(EmpName) OVER(ORDER BY Salary DESC) AS LowestPaidEmployee
    FROM @employees
    WHERE DeptID == 100;
   
OUTPUT @result
TO "/Output/ReferenceGuide/last_value/exampleA.csv"
USING Outputters.Csv();
```

**B.    Using LAST_VALUE over partitions**   
The following example uses `LAST_VALUE` to return the lowest paid employee compared to other employees within the same department.  The [PARTITION BY](over-expression-u-sql.md#OPBC) clause partitions the employees by department and the `LAST_VALUE` function is applied to each partition independently.  The [ORDER BY](over-expression-u-sql.md#OBC) clause specified in the [OVER](over-expression-u-sql.md) clause determines the logical order in which the `LAST_VALUE` function is applied to the rows in each partition.
```
@result =
    SELECT DeptName,
           EmpName,
           Salary,
           LAST_VALUE(EmpName) OVER(PARTITION BY DeptID ORDER BY Salary DESC) AS LowestPaidEmployeePerDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/last_value/exampleB.csv"
USING Outputters.Csv();
```

**C.    Using FIRST_VALUE and LAST_VALUE in a computed expression**   
The following example uses the `FIRST_VALUE` and `LAST_VALUE` functions in computed expressions to show the salary difference between the highest and lowest paid employee.  The `LAST_VALUE` function returns the lowest salary for a department, and subtracts it from the current employee's salary.  The `FIRST_VALUE` function returns the highest salary for a department, and subtracts it from the current employee's salary. 
```
@result =
    SELECT DeptName,
           EmpName,
           Salary,
           Salary - LAST_VALUE(Salary) OVER(PARTITION BY DeptID ORDER BY Salary DESC) AS AmountOverLowestPaidPerDept,
           Salary - FIRST_VALUE(Salary) OVER(PARTITION BY DeptID ORDER BY Salary DESC) AS AmountUnderHighestPaidPerDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/last_value/exampleC.csv"
ORDER BY DeptName ASC,
         Salary DESC
USING Outputters.Csv();
```

### See Also 
* [Analytic Functions (U-SQL)](analytic-functions-u-sql.md)  
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
