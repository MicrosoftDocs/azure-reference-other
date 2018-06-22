---
title: "FIRST_VALUE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 2f5cd094-2634-4430-9e95-e87f43d0a32c
caps.latest.revision: 7
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# FIRST_VALUE (U-SQL)
The `FIRST_VALUE` analytic function returns the first value in an ordered set of values provided by the windowing expression. 

`FIRST_VALUE` can only be used in the context of a [windowing expression](over-expression-u-sql.md). 

## Syntax
<pre>
FIRST_VALUE_Expression := 
    'FIRST_VALUE' '(' <a href="#exp">expression</a> ')'.
</pre>

## Semantics of Syntax Elements 
* <a name="exp"></a>**`expression`**     
The expression for which the first value gets calculated for the window.

## Return Type 
The nullable type of the input. 

## Usage in Windowing Expression 
This analytic function can be used in a [windowing expression](over-expression-u-sql.md) with the following restrictions: 
* The [ORDER BY](over-expression-u-sql.md#OBC) clause in the [OVER](over-expression-u-sql.md) operator is required. 

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The example(s) below are based on the dataset(s) defined below.  Ensure your execution includes the rowset variable(s).

**Dataset**  
```sql
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
        (9, "Ethan",  "Marketing",   400, 15000),
        (10, "Ava",   "Marketing",   400, 9000) 
        ) AS T(EmpID, EmpName, DeptName, DeptID, Salary);
```
<br />


**Using FIRST_VALUE**  
The following example uses `FIRST_VALUE` to return the name of the highest paid employee for a given department.
```sql
@result =
    SELECT DISTINCT
           FIRST_VALUE(EmpName) OVER(ORDER BY Salary DESC) AS HighestPaidEngineer
    FROM @employees
    WHERE DeptID == 100;
   
OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/first_value/example1A.txt"
USING Outputters.Tsv(outputHeader: true);


// Alternative method without FIRST_VALUE
@result = 
    SELECT e.EmpName AS HighestPaidEngineer
    FROM @employees AS e
    JOIN (SELECT (int)MAX(Salary) AS MaxSalary FROM @employees WHERE DeptID == 100) AS sc
    ON e.Salary == sc.MaxSalary
    WHERE DeptID == 100;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/first_value/example1B.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Using FIRST_VALUE over partitions**  
The following example uses `FIRST_VALUE` to return the highest and lowest paid employee from each department.   
The [PARTITION BY](over-expression-u-sql.md#OPBC) clause partitions the employees by department and the `FIRST_VALUE` function is applied to each partition independently.   
The [ORDER BY](over-expression-u-sql.md#OBC) clause specified in the [OVER](Over%20\(U-SQL\):%20Windowing%20Expression.md) clause determines the logical order in which the `FIRST_VALUE` function is applied to the rows in each partition.
```sql
@result =
    SELECT DISTINCT
           DeptName,
           FIRST_VALUE(EmpName) OVER(PARTITION BY DeptID ORDER BY Salary DESC) AS HighestPaidEmployeeByDept,
           FIRST_VALUE(EmpName) OVER(PARTITION BY DeptID ORDER BY Salary ASC) AS LowestPaidEmployeeByDept
    FROM @employees;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/first_value/example2A.txt"
USING Outputters.Tsv(outputHeader: true);

// Additional examples and contrasting with MAX and MIN
@result =
    SELECT DISTINCT
           DeptName,
           FIRST_VALUE(EmpName) OVER(PARTITION BY DeptID ORDER BY Salary DESC) AS HighestPaidEmployeePerDept,
           FIRST_VALUE(Salary) OVER(PARTITION BY DeptID ORDER BY Salary DESC) AS HighestSalaryPerDept,
           MAX(Salary) OVER(PARTITION BY DeptID ORDER BY Salary DESC ROWS UNBOUNDED PRECEDING) AS HighestSalaryPerDept2,
           FIRST_VALUE(EmpName) OVER(PARTITION BY DeptID ORDER BY Salary ASC) AS LowestPaidEmployeePerDept,
           FIRST_VALUE(Salary) OVER(PARTITION BY DeptID ORDER BY Salary ASC) AS LowestSalaryPerDept,
           MIN(Salary) OVER(PARTITION BY DeptID ORDER BY Salary ROWS UNBOUNDED PRECEDING) AS LowestSalaryPerDept2
    FROM @employees;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/first_value/example2B.csv"
USING Outputters.Csv(outputHeader: true);
```
<br />


**Using FIRST_VALUE in a computed expression**  
The following example uses `FIRST_VALUE` in computed expressions to show the salary difference between the highest and lowest paid employee from each department.
```sql
@result =
    SELECT DeptName,
           EmpName,
           Salary,
           FIRST_VALUE(Salary) OVER(PARTITION BY DeptID ORDER BY Salary DESC) - Salary AS AmountUnderHighestPaidPerDept,
           Salary - FIRST_VALUE(Salary) OVER(PARTITION BY DeptID ORDER BY Salary ASC) AS AmountOverLowestPaidPerDept
    FROM @employees;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/first_value/example3.csv"
ORDER BY DeptName ASC, Salary DESC
USING Outputters.Csv(outputHeader: true);
```
<br />

**FIRST_VALUE using OVER() and the ROWS clause**  
The `OVER` expression in the following query defines the window by partitioning the rowset on DeptID. 
The `ROWS` clause further limits the rows in the partition by specifying fixed number of rows preceding or following the current row.  
Query returns the highest paid employee by department for the given window.
```sql
@result =
    SELECT DeptName,
           EmpName,
           Salary,
           FIRST_VALUE(EmpName) OVER(PARTITION BY DeptID ORDER BY Salary DESC ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS threeRowWindow_2PriorAndCurrent_ByDeptID,
           FIRST_VALUE(EmpName) OVER(PARTITION BY DeptID ORDER BY Salary DESC ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING) AS threeRowWindow_1Prior_Current_1Following_ByDeptID,
           FIRST_VALUE(EmpName) OVER(ORDER BY Salary DESC ROWS UNBOUNDED PRECEDING) AS rollingWindow_allRows,
           FIRST_VALUE(EmpName) OVER(PARTITION BY DeptID ORDER BY Salary DESC ROWS UNBOUNDED PRECEDING) AS rollingWindow_ByDeptID
    FROM @employees
    WHERE DeptID IN (100, 400);

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/first_value/example4.csv"
ORDER BY DeptName, Salary DESC
USING Outputters.Csv(outputHeader: true);
```
<br />


## See Also 
* [Analytic Functions (U-SQL)](analytic-functions-u-sql.md)  
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 


