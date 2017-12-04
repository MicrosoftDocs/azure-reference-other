---
title: "U-SQL Statistics | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 9a4bafc9-e34e-4097-9867-8cf980d802de
caps.latest.revision: 15
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Statistics
In order to provide more information to the query optimizer about the data characteristics stored inside a table, such as the value distribution etc., U-SQL provides statistics on the tables. For most queries, the query optimizer already generates the necessary statistics for a high-quality query plan; in a few cases, you need to create additional statistics with [CREATE STATISTICS](create-statistics-u-sql.md) or modify the query design to improve query performance.  
  
### Statistics DDL Statements
The following statements are supported:  

<table><th align="left">Syntax</th><tr><td><pre>
Statistics_DDL_Statement :=                                                                              
     <a href="create-statistics-u-sql.md">Create_Statistics_Statement</a>  
|    <a href="update-statistics-u-sql.md">Update_Statistics_Statement</a>  
|    <a href="drop-statistics-u-sql.md">Drop_Statistics_Statement</a>.  
</pre></td></tr></table>
  
### See Also
- [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)

