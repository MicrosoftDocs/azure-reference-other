---
title: "Data Modification Language (DML) Statements (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-07-31"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 1edce2d1-1e57-4493-ac2b-3e11acb68704
caps.latest.revision: 18
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Data Modification Language (DML) Statements (U-SQL)
U-SQL currently only provides a limited set of statements that persist data and no statement that directly changes persisted data.  
  
U-SQL offers the ability to persist data either as unstructured files with the [OUTPUT](output-statement-u-sql.md) statement or as rows inside structured managed tables with either the [INSERT](insert-u-sql.md) statement or while creating a table from a query result with [CREATE TABLE … AS](create-table-u-sql-creating-a-table-from-a-query.md).  
  
If data that already is in a table needs to be updated, the table needs to be recomputed.
  
## U-SQL DML Statements
<table><th align="left">Syntax</th><tr><td><pre>
DML_Statement :=                                                                                         
    <a href="insert-u-sql.md">INSERT</a>.
</pre></td></tr></table>
  
### See Also
* [INSERT (U-SQL)](insert-u-sql.md) 
* [OUTPUT Statement (U-SQL)](output-statement-u-sql.md)  
* [CREATE TABLE (U-SQL): Creating a Table from a Query](create-table-u-sql-creating-a-table-from-a-query.md)   
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)

