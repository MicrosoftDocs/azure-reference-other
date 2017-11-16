---
title: "AND (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-30"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e1378464-5d01-45d6-9691-0a5b6d912a67
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# AND (U-SQL)
U-SQL’s logical AND operator performs a conjunction of two Boolean expressions and returns false if at least one of the two expression is false and returns true if both expressions are true. Unlike the equivalent C# [&&](https://msdn.microsoft.com/library/c6s3h5a7.aspx) expression, AND will not preserve the execution order and will not short-cut the expression evaluation. 

When more than one logical operator is used in an expression, AND operators bind stronger than [OR](or-u-sql.md) and weaker than [NOT](not-u-sql.md). Parentheses can be used to change the binding precedence. 

<table><th>Syntax</th><tr><td><pre>
AND_Expression :=                                                                                        
      <a href="#bn_exp">Boolean_Expression</a> 'AND' <a href="#bn_exp">Boolean_Expression</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="bn_exp"></a>**`Boolean_Expression`**    
The two Boolean expressions to be combined that return a not-null value of type bool.  

### Return Type 
[bool](other-simple-built-in-types-and-literals.md) 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

```
@data  = 
    SELECT * FROM 
        (VALUES  
        (1, "Noah",   100, (int?)10000, new DateTime(2012,05,31)),
        (2, "Sophia", 100, (int?)15000, new DateTime(2012,03,19)),
        (3, "Liam",   100, (int?)30000, new DateTime(2014,09,14)),
        (6, "Emma",   200, (int?)8000,  new DateTime(2014,03,08)),
        (7, "Jacob",  200, (int?)8000,  new DateTime(2014,09,02)),
        (8, "Olivia", 200, (int?)8000,  new DateTime(2013,12,11)),
        (9, "Mason",  300, (int?)50000, new DateTime(2016,01,01)),
        (10, "Ava",   400, (int?)15000, new DateTime(2014,09,14)),
        (11, "Ethan", 400, (int?)null,  new DateTime(2015,08,22))
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate);

@result =
    SELECT * FROM @data
    WHERE DeptID == 100 AND Salary > 10000;

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/And1.txt" USING Outputters.Csv();

// alternative
@result =
    SELECT * FROM @data
    WHERE DeptID == 100 && Salary > 10000;

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/And2.txt" USING Outputters.Csv();
```

### See Also 
* [Logical Operators (U-SQL)](logical-operators-u-sql.md)
* [NOT (U-SQL)](not-u-sql.md)  
* [OR (U-SQL)](or-u-sql.md)  
