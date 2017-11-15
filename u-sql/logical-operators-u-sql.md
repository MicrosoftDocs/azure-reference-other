---
title: "Logical Operators (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 5fe94e0a-4b53-446d-85aa-5619599c51ec
caps.latest.revision: 8
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Logical Operators (U-SQL)
U-SQL supports the C# logical operators [&&](https://msdn.microsoft.com/library/2a723cdk.aspx), [||](https://msdn.microsoft.com/library/6373h346.aspx) and [!](https://msdn.microsoft.com/library/f2kd6eb2.aspx) (not). Since C# guarantees order of execution and provides short-cutting on logical operators, these operators can incur a slight performance penalty. The C# semantics does not allow the optimizer to rewrite and reorder the query predicates. For example, the second predicate in a logical expression cannot be moved up in the execution tree to apply the filter early, because it would now be executed before the first predicate. 

Since such query rewrites are often useful to improve query performance, U-SQL also supports the SQL-inspired [AND](../USQL/and-u-sql.md), [OR](../USQL/or-u-sql.md) and [NOT](../USQL/not-u-sql.md) operators. In order to give the optimizer better choices, these operators should be used instead of the C# operators if the execution order among the two predicates does not need to be preserved.  

When more than one logical operator is used in an expression, [NOT](../USQL/not-u-sql.md) operators bind stronger than [AND](../USQL/and-u-sql.md) which in turn bind stronger than [OR](../USQL/or-u-sql.md). Parentheses can be used to change the binding precedence. 

Note that unlike the ANSI SQL operators, these operators are still operating according to C#’s two-valued Boolean Logic, meaning that they do not support null values as a third logical value. 

Logical Operators build up the Boolean_Expression as follows: 

<table><th align="left">Syntax</th><tr><td><pre>
Boolean_Expression :=                                                                                       
     <a href="#b_exp">bool_expression</a> 
|    ('<a href="#NOR">NOT</a>' | '<a href="#lops">!</a>') Boolean_Expression 
|    Boolean_Expression ('<a href="#NOR">AND</a>' | '<a href="#lops">&&</a>') Boolean_Expression 
|    Boolean_Expression ('<a href="#NOR">OR</a>' | '<a href="#lops">||</a>') Boolean_Expression.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="b_exp"></a>**`bool_expression`**  
A C# Boolean expression that returns a not-null value of type bool.  

* <a name="lops"></a>**`!, &&, ||`**  
C# logical operators that provide shortcutting and preserve order of expressions. 
 
* <a name="NOR"></a>**`NOT, AND, OR`**   
U-SQL logical operators that provide faster execution with predicate reordering. 

### See Also 
* [AND (U-SQL)](../USQL/and-u-sql.md)  
* [NOT (U-SQL)](../USQL/not-u-sql.md)  
* [OR (U-SQL)](../USQL/or-u-sql.md)  
* [Built-in Functions (U-SQL)](../USQL/built-in-functions-u-sql.md) 
* [Comparison Operators (U-SQL)](../USQL/comparison-operators-u-sql.md)  
* [C# Operators](https://msdn.microsoft.com/library/6a71f45d.aspx)  

