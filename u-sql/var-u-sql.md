---
title: "VAR (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e4bb69b4-6e16-49d8-93a1-b85d14a3f4b1
caps.latest.revision: 6
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# VAR (U-SQL)
The VAR aggregator returns the statistical variance of all nonnull values in the group or returns null if all the input values are null. The values have to be numeric or an error is raised. 

The identity value is null. 

<table><th align="left">Syntax</th><tr><td><pre>
VAR_Expression :=                                                                                        
     'VAR' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**    
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation.  

* <a name="exp"></a>**`expression`**    
The C# expression (including column references) that gets aggregated. The type of the expression has to be a numeric type or an error is raised. 

### Return Type 
The return type is [double?](numeric-types-and-literals.md). 

### Usage in Windowing Expression 
This aggregator can be used in a [windowing expression](over-expression-u-sql.md) without any additional restrictions. 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  

   ```sql
    @employees = 
        SELECT * FROM 
            ( VALUES
            (1, "Noah",   "Engineering", 100, 10000),
            (2, "Sophia", "Engineering", 100, 20000),
            (3, "Liam",   "Engineering", 100, 30000),
            (4, "Emma",   "HR",          200, 8000),
            (5, "Jacob",  "HR",          200, 8000),
            (6, "Olivia", "HR",          200, 8000),
            (7, "Mason",  "Executive",   300, 50000),
            (8, "Ava",    "Marketing",   400, 15000),
            (9, "Ethan",  "Marketing",   400, 9000) 
            ) AS T(EmpID, EmpName, DeptName, DeptID, Salary);
   ```

**A.    Using VAR**   
The following query returns the statistical variance for all: 1) salary values, and 2) distinct salary values.
```sql
@result =
    SELECT VAR(Salary) AS VAR_AllSalaries,
           VAR(DISTINCT Salary) AS VAR_DistinctSalaries
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/var/exampleA.csv"
USING Outputters.Csv();
```

**B.    VAR per group**   
The following query determines the salary statistical variance for each department with the [GROUP BY](group-by-and-having-clauses-u-sql.md) clause.
```sql
@result =
    SELECT DeptName,
           VAR(Salary) AS VARSalaryByDept
    FROM @employees
    GROUP BY DeptName;

OUTPUT @result
TO "/Output/ReferenceGuide/var/exampleB.csv"
USING Outputters.Csv();
```

**C.    VAR with OVER()**   
The [OVER](over-expression-u-sql.md) clause in the following query is empty which defines the "window" to include all rows.  The query determines the salary statistical variance over the window - all employees.
```sql
@result =
    SELECT EmpName,
           VAR(Salary) OVER() AS VAR_AllSalaries
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/var/exampleC.csv"
USING Outputters.Csv();
```

**D.    VAR over a defined window using OVER()**   
The [OVER](over-expression-u-sql.md) clause in the following query is `DeptName`.  The query returns `EmpName`, `DeptName`, `Salary`, and the salary statistical variance over the window - `DeptName`.
```sql
@result =
    SELECT EmpName,
           DeptName,
           Salary,
           VAR(Salary) OVER(PARTITION BY DeptName) AS VARSalaryByDept
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/var/exampleD.csv"
USING Outputters.Csv();
```

### See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)  
* [VARP (U-SQL)](varp-u-sql.md)
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 



