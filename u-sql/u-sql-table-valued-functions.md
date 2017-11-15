---
title: "U-SQL Table-valued Functions | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 73fe3c6b-d2e2-49c5-bee2-992b44cae407
caps.latest.revision: 10
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Table-valued Functions
U-SQL provides the ability to wrap a sequence of [query statements](query-statements-and-expressions-u-sql.md) into a function that returns the resulting rowset and parameterize it. U-SQL table-valued functions are stored in the metadata catalog and can be shared with other users.  

### Table-Valued Function DDL Statements    
The following statements manage the functions:

<table><th align="left">Syntax</th><tr><td><pre>
TV_Function_DDL_Statement :=                                                                             
     <a href="create-function-u-sql-table-valued-function.md">Create_TV_Function_Statement</a>
|    <a href="drop-function-u-sql.md">Drop_TV_Function_Statement</a>
</pre></td></tr></table>

Please follow the links for more details on using table-valued functions.   

A U-SQL table-valued function can be invoked and used like any other [primary query expression](query-statements-and-expressions-u-sql.md), including being assigned to a [rowset variable](query-statements-and-expressions-u-sql.md) or used in a SELECT [FROM clause](from-clause-u-sql.md).  

They always will be inlined in the invoking expression context but encapsulate their own lexical and runtime context such as their own local default schema and database context, their own local variables etc.  
  
A function with a single resulting rowset, defined by a single query expression and no parameters is equivalent to a [view](u-sql-views.md).  
  
### See Also
* [U-SQL Functions](u-sql-functions.md)  
* [CREATE FUNCTION (U-SQL): Table-valued Function](create-function-u-sql-table-valued-function.md)  
* [DROP FUNCTION (U-SQL)](drop-function-u-sql.md)  
* [Table-Valued Function Expression (U-SQL)](table-valued-function-expression-u-sql.md)   
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)   
