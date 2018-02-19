---
title: "COUNT (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 90746132-b0f2-49b4-8926-6162f935427c
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# COUNT (U-SQL)
The COUNT aggregator returns the number of items in a group. If COUNT(*) is specified the count will include null values, if an expression or column reference is provided, then null values will not be counted. 

The identity value is 0. 

<table border="1" width="100%"><th align="left">Syntax</th><tr><td><pre>
COUNT_Expression := 
    'COUNT' '(' ['<a href="#dist">DISTINCT</a>'] (<a href="#exp">expression | '*'</a>) ')'.  
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**  
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation.  

* <a name="exp"></a>**`expression | *`**   
The C# expression (including column references) for which the nonnull values in a group get counted or * to indicate to count the rows and include null values in the count. 

### Return Type 
The return type is [long?](numeric-types-and-literals.md). 

### Usage in Windowing Expression 
This aggregator can be used in a [windowing expression](over-expression-u-sql.md) without any additional restrictions. 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure you create and populate the table in a separate window before executing the examples.

```sql
DROP TABLE IF EXISTS master.dbo.Employees;

CREATE TABLE master.dbo.Employees
(
    EmpID int,
    EmpName string,
    DeptName string,
    DeptID int,
    Salary int,
    INDEX cl_idx CLUSTERED(EmpID ASC) PARTITIONED BY HASH(EmpID)
);

INSERT INTO master.dbo.Employees
(EmpID, EmpName, DeptName, DeptID, Salary)
VALUES
(1, "Noah",   "Engineering", 100, 10000),
(2, "Sophia", "Engineering", 100, 20000),
(3, "Liam",   "Engineering", 100, 30000),
(4, "Emma",   "HR",          200, 10000),
(5, "Jacob",  "HR",          200, 10000),
(6, "Olivia", "HR",          200, 10000),
(7, "Mason",  "Executive",   300, 50000),
(8, "Ava",    "Marketing",   400, 15000),
(9, "Ethan",  "Marketing",   400, 10000);

INSERT INTO master.dbo.Employees
(EmpID, EmpName, DeptID, Salary)
VALUES
(10, "David", 800, 100);
```

**A.    Count of all values**  
The following query calculates the: 1) total record count, 2) total department count, and 3) distinct number of departments.
```sql
@result =
    SELECT COUNT( * ) AS TotalRecordCount,
           COUNT(DeptName) AS DeptNameCount,
           COUNT(DISTINCT DeptName) AS DistinctDeptNameCount
    FROM master.dbo.Employees;

OUTPUT @result
TO "/Output/ReferenceGuide/count/exampleA.csv"
USING Outputters.Csv();
```

**B.    Count values per group**  
The following query calculates the count of employees within each department with the [GROUP BY](group-by-and-having-clauses-u-sql.md) clause.
```sql
@result =
    SELECT DeptName,
           COUNT( * ) AS EmpNameByDeptCount
    FROM master.dbo.Employees
    GROUP BY DeptName;

OUTPUT @result
TO "/Output/ReferenceGuide/count/exampleB.csv"
USING Outputters.Csv();
```

**C.    Count values with OVER()**  
The [OVER](over-expression-u-sql.md) clause in the following query is empty which defines the "window" to include all rows. The query calculates the employee count over the window - all employees.
```sql
@result =
    SELECT EmpName,
           COUNT( * ) OVER() AS EmpNameCount
    FROM master.dbo.Employees;

OUTPUT @result
TO "/Output/ReferenceGuide/count/exampleC.csv"
USING Outputters.Csv();
```

**D.    Count values over a defined window using OVER()**  
The [OVER](over-expression-u-sql.md) clause in the following query is DeptName.  The query returns all records and the number of employees over the window - DeptName.
```sql
@result =
    SELECT *,
           COUNT( * ) OVER(PARTITION BY DeptName) AS EmpNameByDeptCount
    FROM master.dbo.Employees;

OUTPUT @result
TO "/Output/ReferenceGuide/count/exampleD.csv"
USING Outputters.Csv();
```

### See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
