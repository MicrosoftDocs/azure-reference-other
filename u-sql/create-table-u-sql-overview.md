---
title: "CREATE TABLE (U-SQL): Overview | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: f7fdd48d-ecd5-4901-9f04-c460280b00ee
caps.latest.revision: 16
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CREATE TABLE (U-SQL): Overview
U-SQL provides the ability to create both [managed and external tables](../USQL/u-sql-tables.md#man_ext_tabls) as well as creating partitioned managed tables. Please follow the links in the following grammar rule to the respective sections.  

<table><th>Syntax</th><tr><td><pre>
Create_Table_Statement :=                                                                                
        <a href="create-table-u-sql-creating-managed-tables.md">Create_Managed_Table_Statement</a>   
|       <a href="create-external-table-u-sql.md">Create_External_Table_Statement</a>.  
</pre></td></tr></table>
  
### See Also
* [ALTER TABLE (U-SQL): Adding and Removing Vertical Partition Buckets](../USQL/alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md) 
* [TRUNCATE TABLE (U-SQL)](../USQL/truncate-table-u-sql.md)
* [DROP TABLE (U-SQL](../USQL/drop-table-u-sql.md) 
