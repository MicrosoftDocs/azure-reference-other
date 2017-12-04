---
title: "DROP TABLE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 12022cbf-c922-42f4-9845-40e57feb7fff
caps.latest.revision: 16
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# DROP TABLE (U-SQL)
The statement drops the specified table and deletes all the data contained within from the system.   
  
> [!WARNING]
> **This operation cannot be undone!**

<table><th align="left">Syntax</th><tr><td><pre>
Drop_Table_Statement :=                                                                                  
    'DROP' 'TABLE' [<a href="#IE">'IF' 'EXISTS'</a>] <a href="#ident">Identifier</a>.
</pre></td></tr></table>
  
### Semantics of Syntax Elements  
-    <a name="ident"></a>**`Identifier`**    
Identifies the table to be dropped. If the Identifier is a three-part identifier, the table will be dropped from the specified database and schema. If the Identifier is a two-part identifier, then the table of the given schema and of the given name of the current static database context will be dropped. If the identifier is a simple identifier, then the table of the given name in the current static database and schema context will be dropped.
 
      If a table of the given name does not exist, or the user has no permissions to drop the table, an error is raised.  
  
-    <a name="IE"></a>**`IF EXISTS`**    
    If the optional `IF EXISTS` is specified, then the statement drops the table if it already exists, or succeeds without changes if the table does not exist or the user has no permission to at least enumerate all existing tables.     
    
### Example  
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
  
The following script shows how the `SampleTable` in the `TestReferenceDB` database’s default schema is deleted if it already exists before it is recreated:  
```  
DROP TABLE IF EXISTS TestReferenceDB..SampleTable;  
  
CREATE TABLE TestReferenceDB..SampleTable AS (id int);  
```  
### See Also  
* [U-SQL Tables](u-sql-tables.md) 
* [CREATE TABLE (U-SQL): Overview](create-table-u-sql-overview.md)  
* [ALTER TABLE (U-SQL): Adding and Removing Vertical Partition Buckets](alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md)
* [TRUNCATE TABLE (U-SQL)](truncate-table-u-sql.md) 
  
