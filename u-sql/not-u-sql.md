---
title: "NOT (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-30"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 312e516b-d09e-451d-81d5-b79a7164b155
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# NOT (U-SQL)
U-SQL’s logical NOT operator performs a negation of the Boolean expression and returns false if the expression evaluates to true and true if it evaluates to false. It is equivalent to the C# ! operator. 

When more than one logical operator is used in an expression, NOT operators bind stronger than [AND](and-u-sql.md) and [OR](or-u-sql.md). Parentheses can be used to change the binding precedence. 

<table><th>Syntax</th><tr><td><pre>
NOT_Expression :=                                                                                        
    'NOT' <a href="#bn_exp">Boolean_Expression</a>.  
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="bn_exp"></a>**`Boolean_Expression`**    
The Boolean expression to be negated that returns a not-null value of type bool.  

### Return Type 
[bool](other-simple-built-in-types-and-literals.md)

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

Return all records where `EmpName` does not start with E.
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
    WHERE NOT EmpName.StartsWith("E");

OUTPUT @result TO "ReferenceGuide/Operators/Logical/Not1.txt" USING Outputters.Csv();

// alternative
@result =
    SELECT * FROM @data
    WHERE  !EmpName.StartsWith("E");

OUTPUT @result TO "ReferenceGuide/Operators/Logical/Not2.txt" USING Outputters.Csv();

// alternative
@result =
    SELECT * FROM @data
    WHERE  EmpName NOT LIKE "E%";

OUTPUT @result TO "ReferenceGuide/Operators/Logical/Not3.txt" USING Outputters.Csv();
```

### See Also 
* [Logical Operators (U-SQL)](logical-operators-u-sql.md)  
* [AND (U-SQL)](and-u-sql.md)  
* [OR (U-SQL)](or-u-sql.md)  



