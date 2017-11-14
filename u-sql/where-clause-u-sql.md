---
title: "WHERE Clause (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: d46f3b30-2754-4ea5-b7eb-5af1df8d8def
caps.latest.revision: 13
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# WHERE Clause (U-SQL)
The optional `WHERE` clause in a [SELECT](select-expression-u-sql.md) expression will filter the rowset that the [FROM](from-clause-u-sql.md) clause calculated.  
  
<table><th>Syntax</th><tr><td><pre>
Where_Clause :=                                                                                          
    'WHERE' <a href="#BE">Boolean_Expression</a>.                            
</pre></td></tr></table>
  
### Semantics of Syntax Elements    
- <a name="BE"></a>**`Boolean_Expression`**   
Specifies the Boolean predicate that acts as the filter.  
  
  <table><th>Syntax</th><tr><td><pre>
Boolean_Expression :=                                                                               
      bool_expression
|     ('<a href="not-u-sql.md">NOT</a>' | '!') Boolean_Expression
|     Boolean_Expression ('<a href="and-u-sql.md">AND</a>' | '&&') Boolean_Expression
|     Boolean_Expression ('<a href="or-u-sql.md">OR</a>' | '||') Boolean_Expression.
</pre></td></tr></table>
      
    The predicate can either be any C# expression that evaluates to a bool, or a negation of a Boolean expression, a conjunction or a disjunction. U-SQL’s Boolean logic is based on C# and thus is like in C# 2-valued logic where null == null evaluates to `true` and null == 1 will evaluate to `false`.  
  
    The expressions can of course refer to any of the columns in the rowset, can invoke any C# expression and function and method call as long as the functions and methods are included in the scope either implicitly or explicitly.  
  
    The [AND](and-u-sql.md) and [OR](or-u-sql.md) operators do not guarantee execution order of their operands to allow the query processor to reorder them for better performance. If the order is important, for example to guard a subsequent expression from a runtime error like a null exception, one should use C#’s [&&](https://msdn.microsoft.com/library/2a723cdk.aspx) and [||](https://msdn.microsoft.com/library/6373h346.aspx) which will preserve the expression’s execution order from left to right and will shortcut the expression if the left side of the logical expression determines the outcome.  
  
### Examples    
The following query finds all the search session in the @searchlog rowset that are in the `en-gb` region.  
  
```  
@rs1 =  
    SELECT Start, Region, Duration  
    FROM @searchlog  
    WHERE Region == "en-gb";
```
  
Note the use of `==` in the example above instead of `=`. This is because expressions in the `SELECT` statement are true C# expressions where `==` is the comparison operator for equality.  
  
The following example shows a more complex combination of [AND](and-u-sql.md) and [OR](or-u-sql.md). It finds all the search sessions from the @searchlog rowset that lasted between 2 and 5 minutes or are in the en-gb region.  
  
```  
@rs2 =  
    SELECT Start, Region, Duration  
    FROM @searchlog  
    WHERE (Duration >= 2*60 AND Duration <= 5*60) OR (Region == "en-gb");
```
  
While U-SQL supports the [BETWEEN](between-u-sql.md) comparison operation, the following example shows how to use [AND](and-u-sql.md) and the DateTime.Parse() method to filter between two dates:  
  
```  
@rs3 =  
    SELECT Start, Region, Duration  
    FROM @searchlog  
    WHERE Start >= DateTime.Parse("2012/02/16") AND Start <= DateTime.Parse("2012/02/17");
```
  
Assuming the Region can contain null values and one wants to check if the first three characters correspond to the regions that start with "de-", one should use the C# [&&](https://msdn.microsoft.com/library/2a723cdk.aspx) operator to guarantee that the null check occurs before applying the string operations and to short-circuit the expression if the check fails:  
  
```  
@rs4 =  
    SELECT Start, Region, Duration  
    FROM @searchlog  
    WHERE Start >= DateTime.Parse("2012/02/16") AND Start <= DateTime.Parse("2012/02/17")  
    AND (Region != null && Region.StartsWith("de-"));
```
  
### See Also 
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md) 
* [SELECT Expression (U-SQL)](select-expression-u-sql.md) 
* [Output Statement (U-SQL)](output-statement-u-sql.md)  
* [Logical Operators (U-SQL)](logical-operators-u-sql.md) 
