---
title: "U-SQL Indexes | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6bb45dac-f231-461c-9da2-0862ab9d7d2e
caps.latest.revision: 15
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Indexes
One of the benefits of storing data in a structured container such as a table is to have index structures to make data lookup faster.  
  
### Index DDL Statements    
The following are the supported operations on indexes:  
  
<table><th align="left">Syntax</th><tr><td><pre>
Index_DDL_Statement :=                                                                                   
     <a href="create-index-u-sql.md">Create_Index_Statement</a>.
</pre></td></tr></table>
  
U-SQL at the moment supports only clustered indexes that are used to cluster the associated U-SQL tables according to the index keys. Since the table then is physically stored as that index, there can only be one clustered index per table and one cannot delete a clustered index. Instead one [drops the table](drop-table-u-sql.md).  
  
Alternative indexes such as column store indexes and secondary indexes that give you support for secondary access patterns are planned for future releases.  

### See Also
* [CREATE INDEX (U-SQL)](create-index-u-sql.md)  
* [DROP INDEX (U-SQL)](drop-index-u-sql.md)  
* [CREATE TABLE (U-SQL): Creating a Table from a Query](create-table-u-sql-creating-a-table-from-a-query.md)  
* [CREATE TABLE (U-SQL): Creating a Table with Schema](create-table-u-sql-creating-a-table-with-schema.md)  
* [DROP TABLE (U-SQL)](drop-table-u-sql.md) 
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)

