---
title: "OR (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-30"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e425e9f0-b531-48d3-8a3f-2e0068ad12bd
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# OR (U-SQL)
U-SQL’s logical OR operator performs a disjunction of two Boolean expressions and returns true if at least one of the two expression is true and returns false if both expressions are false. Unlike the equivalent C# [||](https://msdn.microsoft.com/library/f355wky8.aspx) expression, OR will not preserve the execution order and will not short-cut the expression evaluation. 

When more than one logical operator is used in an expression, OR operators bind weaker than both [AND](and-u-sql.md) and [NOT](not-u-sql.md). Parentheses can be used to change the binding precedence. 

<table><th align="left">Syntax</th><tr><td><pre>
OR_Expression :=                                                                                         
     <a href="#bn_exp">Boolean_Expression</a> 'OR' <a href="#bn_exp">Boolean_Expression</a>.
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
    WHERE DeptID == 100 OR DeptID == 400;

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Or1.txt" USING Outputters.Csv();


@result =
    SELECT * FROM @data
    WHERE DeptID == 100 OR Salary > 10000;

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Or2.txt" USING Outputters.Csv();


@result =
    SELECT * FROM @data
    WHERE (DeptID == 100 AND Salary > 10000) OR DeptID == 400;

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Or3.txt" USING Outputters.Csv();


@result =
    SELECT * FROM @data
    WHERE (DeptID == 100 OR DeptID == 400) AND Salary > 10000;

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Or4.txt" USING Outputters.Csv();
```


### See Also 
* [Logical Operators (U-SQL)](logical-operators-u-sql.md) 
* [AND (U-SQL)](and-u-sql.md)   
* [NOT (U-SQL)](not-u-sql.md)   



