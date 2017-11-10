---
title: "U-SQL Databases | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: f92f6bcf-d800-4eea-b9a3-513bf63bd139
caps.latest.revision: 15
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Databases
Similar to other database systems and SQL-inspired Big Data processing systems such as Hive, U-SQL uses the concept of a database to group related objects together.   
  
U-SQL provides a built-in database called `master` that will be used as the default database context and it provides the ability to create and delete additional databases with the following DDL statements.  
  
The default database context can be changed with the [`USE DATABASE`](../USQL/use-database-u-sql.md) statement.  
  
### Database DDL Statements
<table><th>Syntax</th><tr><td><pre>
DB_DDL_Statement :=                                                                                      
    <a href="create-database-u-sql.md">Create_Database_Statement</a>  
|   <a href="drop-database-u-sql.md">Drop_Database_Statement</a>.  
</pre></td></tr></table>
  
### See Also  
* [CREATE DATABASE (U-SQL)](../USQL/create-database-u-sql.md)  
* [USE DATABASE (U-SQL)](../USQL/use-database-u-sql.md)  
* [DROP DATABASE (U-SQL)](../USQL/drop-database-u-sql.md)  
