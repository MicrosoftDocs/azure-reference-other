---
title: "Expressions (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 1d21962f-ee61-4da3-b075-8d1bd5d1e8df
caps.latest.revision: 13
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# Expressions (U-SQL)
In U-SQL, expressions operate on its typed values. These expressions appear in the context of [U-SQL statements](query-statements-and-expressions-u-sql.md) and consist of a few limited U-SQL operators and the full power of C# expressions.  

While some U-SQL statements allow arbitrary expressions, others may restrict expressions based on the types the expressions are allowed to return, on whether they can be computed at compile time (so called constant-foldable expressions), or even the operators that are allowed in an expression.  
   
The following sections provide the grammar and discussion of some of the more frequently encountered types of expressions. For more details about their use and restrictions in specific statements, please refer to the section on that statement.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Static_String_Expression :=                                                                              
    csharp_string_literal   
|   constant_foldable_string_expression   
|   String_Variable.
</pre></td></tr></table>
  
 

### See Also
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md) 
