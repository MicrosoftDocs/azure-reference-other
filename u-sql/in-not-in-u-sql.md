---
title: "IN, NOT IN (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "05/04/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ac5ad2d0-7882-46a9-bcf8-8ea0c9510aba
caps.latest.revision: 8
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# IN, NOT IN (U-SQL)
U-SQL provides the `IN` and `NOT IN` comparison operators to test for membership in a set of values. It returns true if the value is equal to at least one value in the list, false otherwise for `IN` and true if the value is not in the list and false otherwise for `NOT IN`.  
  
The types of the values to be tested and the members of the test set have to be a [string](textual-types-and-literals.md) or [numeric](numeric-types-and-literals.md) type or null, and have to be compatible with each other, otherwise an error is raised. The comparison operation is using C# equality semantics and string comparisons are culture invariant.  
  
U-SQL does not support the subquery form of the SQL `IN` operator. Most subquery `IN` operations can be transformed to use [SEMIJOIN](semijoin-u-sql.md).  
  
<table><th align="left">Syntax</th><tr><td><pre>
IN_Expression :=                                                                                         
    <a href="#exp">expression</a> ['NOT'] 'IN' '(' <a href="#exp_lst">Expression_List</a> ')'.
</pre></td></tr></table>

### Semantics of Syntax Elements  
- <a name="exp"></a>**`expression`**  
is the expression that creates the value to be tested. It needs to be null or of a [string](textual-types-and-literals.md) or [numeric](numeric-types-and-literals.md) type, otherwise an error is raised.  
  
- <a name="exp_lst"></a>**`Expression_List`**    
is list of expressions that identify the values of the test set.  The maximal supported number of items in the list is 20000.
  
  <table><th>Syntax</th><tr><td><pre>
  Expression_List :=                                                                                  
      expression {',' expression}.
  </pre></td></tr></table>

  The types of the values to be tested and the members of the test set have to be to be null or of a [string](textual-types-and-literals.md) or [numeric](numeric-types-and-literals.md) type and compatible with the value to be tested, otherwise an error is raised. 

### Return Type    
[bool](other-simple-built-in-types-and-literals.md)  
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

```sql
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
    WHERE DeptID IN (100, 400);

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/In1.txt" USING Outputters.Csv();


@result =
    SELECT * FROM @data
    WHERE DeptID NOT IN (100, 400);

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/NotIn1.txt" USING Outputters.Csv();


@result =
    SELECT * FROM @data
    WHERE EmpName IN ("Noah", "Jacob", "Ava");

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/In2.txt" USING Outputters.Csv();
```

### See Also
* [Comparison Operators (U-SQL)](comparison-operators-u-sql.md)  
* [BETWEEN (U-SQL)](between-u-sql.md)  
* [LIKE, NOT LIKE (U-SQL)](like-not-like-u-sql.md)  
* [C# Operators](https://msdn.microsoft.com/library/6a71f45d.aspx)  
