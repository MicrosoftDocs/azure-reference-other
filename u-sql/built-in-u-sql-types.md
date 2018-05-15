---
title: "Built-In U-SQL Types | Microsoft Docs"
ms.custom: ""
ms.date: "04/12/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c351b21d-d84c-417e-bdee-a7ebc0a3413e
caps.latest.revision: 8
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# Built-In U-SQL Types
Any C# type can be used in U-SQL (and C#) expressions, but only a limited subset of them can be used as column types in a rowset. These types are called *built-in U-SQL types*.  
  
Only these built-in U-SQL types can be specified in a schema definition of an [EXTRACT](extract-expression-u-sql.md) or [OUTPUT](output-statement-u-sql.md) statement, in a [CREATE TABLE](create-table-u-sql-creating-a-table-with-schema.md) schema, as a parameter in a [table-valued function](u-sql-table-valued-functions.md), in a [table type](u-sql-table-types.md), in a PRODUCES clause of a [UDO](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-objects--udo) invocation, or can be passed between query statement boundaries.  
 
Built-in U-SQL types can be composed into table types that can be used to define table parameters.  
  
The built-in U-SQL types can be classified into the following types: *simple built-in types* and *complex built-in types*. We use the following grammar to refer to these types.  

<table><th align="left">Syntax</th><tr><td><pre>
Built_in_Type :=                                                                                         
    <a href="simple-built-in-u-sql-types.md">Simple_Type</a> | <a href="complex-built-in-u-sql-types.md">Complex_Type</a>.
</pre></td></tr></table>
  
Their semantics in general follows their C# semantics with a few notable exceptions called out below.  

### U-SQL Type Nullability
Note that unlike SQL data types, where a type is nullable unless specified otherwise, U-SQL types follow the C# rule that non-object types are not nullable per default and have to explicitly be marked as nullable with a question mark `?`, while object types are implicitly nullable and can neither be marked as nullable nor marked as not nullable.  
  

### See Also
* [Data Types and Literals (U-SQL)](data-types-and-literals-u-sql.md) 
* [Simple Built-In U-SQL Types](simple-built-in-u-sql-types.md)  
* [Complex Built-In U-SQL Types](complex-built-in-u-sql-types.md) 
* [IS NULL (U-SQL)](is-null-u-sql.md) 
  
