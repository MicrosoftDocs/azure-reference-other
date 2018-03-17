---
title: "ANY_VALUE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 69303dc9-1581-438f-8b74-8171e6340700
caps.latest.revision: 10
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# ANY_VALUE (U-SQL)
The ANY_VALUE aggregator arbitrarily picks one value from the group including potentially a null value. While the operation picks an arbitrary value, it does so based on the efficiency of execution and not based on some random sampling. 

The identity value is null. 

<table><th align="left">Syntax</th><tr><td><pre>
ANY_VALUE_Expression :=                                                                                  
      'ANY_VALUE' '(' <a href="#exp">expression</a> ')'.</pre></td></tr></table>

### Semantics of Syntax Elements 

* <a name="exp"></a>**`expression`**  
The C# expression (including column references) that gets aggregated. 

### Return Type 
The type of the input. 

### Usage in Windowing Expression 
This aggregator cannot be used in a [windowing expression](over-expression-u-sql.md). 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  

   ```sql
       @employees = 
        SELECT * FROM ( VALUES
            (1, "Noah",   "Engineering", 100, 10000),
            (2, "Sophia", "Engineering", 100, 20000),
            (3, "Liam",   "Engineering", 100, 30000),
            (4, "Emma",   "HR",          200, 10000),
            (5, "Jacob",  "HR",          200, 10000),
            (6, "Olivia", "HR",          200, 10000),
            (7, "Mason",  "Executive",   300, 50000),
            (8, "Ava",    "Marketing",   400, 15000),
            (9, "Ethan",  "Marketing",   400, 10000) )
        AS T(EmpID, EmpName, DeptName, DeptID, Salary);
   ```

**A.  Single arbitrary value**  
The following query selects a single arbitrary `EmpName`. 
```sql
@result =
    SELECT ANY_VALUE(EmpName) AS ArbitraryEmployee
    FROM @employees;
    
OUTPUT @result
TO "/Output/ReferenceGuide/any_value/exampleA.csv"
USING Outputters.Csv();
```

**B.  Arbitrary value per group**  
The following query selects an arbitrary `EmpName` for each `DeptName`.
```sql
@result =
    SELECT DeptName,
           ANY_VALUE(EmpName) AS ArbitraryEmployee
    FROM @employees
    GROUP BY DeptName; 
    
OUTPUT @result
TO "/Output/ReferenceGuide/any_value/exampleB.csv"
USING Outputters.Csv();
```

### See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](over-expression-u-sql.md)
