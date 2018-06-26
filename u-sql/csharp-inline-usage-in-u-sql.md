---
title: "C# Inline Usage in U-SQL | Microsoft Docs"
ms.custom: ""
ms.date: "07/01/2018"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 
caps.latest.revision: 
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# C&#35; Inline Usage in U-SQL
U-SQL’s core reliance on C# for its [U-SQL type](data-types-and-literals-u-sql.md) system and [U-SQL’s expression](expressions-u-sql.md) language provides the query writer access to the wealth of C# and CLR libraries of classes, methods, functions, operators and types. 

All [C# operators](https://msdn.microsoft.com/library/6a71f45d.aspx) except for the assignment operators (=, += etc) are valid in U-SQL. In particular all comparison operators such as `==`, `!=`, `<`, `>` the ternary comparison `cond ? true-expression : false-expression`, the null coalesce operator `??` are supported. Even lambda expressions using `=>` can be used inside U-SQL expressions.  The section [REFERENCE SYSTEM ASSEMBLY](reference-system-assembly-u-sql.md)  provides a list of all preloaded system assemblies and explains how to add additional system assemblies.  

It would go beyond the scope of this documentation to repeat all C# functions and operators, so only the most popular topics will be illustrated.  The topics are mainly limited to examples that illustrate the C# usage in U-SQL.  Please see the relevant C# reference documentation for details.


## C# Inline Usage Example Topics:   
|Topic  |Description|
|----------------|----------------|
|[LINQ](linq-inline-usage-in-u-sql.md) |Language-Integrated Query (LINQ) is the name for a set of technologies based on the integration of query capabilities directly into the C# language. |
|[C# Operators](csharp-functions-and-operators-u-sql.md#sharpOps) |In C#, an operator is a program element that is applied to one or more operands in an expression or statement. |
|[System Namespace](csharp-functions-and-operators-u-sql.md)|The `System` namespace contains fundamental classes and base classes that define commonly-used value and reference data types, events and event handlers, interfaces, attributes, and processing exceptions. |


## See Also 
* [REFERENCE SYSTEM ASSEMBLY](reference-system-assembly-u-sql.md)
* [Built-in Functions (U-SQL)](built-in-functions-u-sql.md)  
* [Built-in U-SQL UDOs](built-in-u-sql-udos.md)  
* [C# Function Variables (U-SQL)](csharp-function-variables-u-sql.md)








