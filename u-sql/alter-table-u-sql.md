---
title: "ALTER TABLE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "06/07/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 4cb50243-3aaa-4949-99d0-31fc6d351b40
caps.latest.revision: 8
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# ALTER TABLE (U-SQL)
Modifies a table definition by adding, or dropping columns.  Adding or dropping a column from a table is a meta data operation only and its performance will not be impacted by the size of the table. 

<table><th>Syntax</th><tr><td><pre>
Alter_Table_Statement :=                                                          
    'ALTER' 'TABLE' <a href="#ident">Identifier</a>   
    ( '<a href="#rebuild">REBUILD</a>'
    | '<a href="#add_drop">ADD</a>' 'COLUMN' <a href="#cdl">Column_Definition_List</a>     
    | '<a href="#add_drop">DROP</a>' 'COLUMN' <a href="#identList">Identifier_List</a> ).  
</pre></td></tr></table>

### Semantics of Syntax Elements  
-    <a name="ident"></a>**`Identifier`**   
Identifies the table to be modified. If the Identifier is a three-part identifier, the table from the specified database and schema will be chosen. If the Identifier is a two-part identifier, then the table of the given schema and of the given name of the current static database context is chosen. If the identifier is a simple identifier, then the table of the given name in the current static database and schema context is chosen.  
    
      If the specified table does not exist, is an external table, or the user does not have permissions to modify the table, an error is raised. 
      
-    <a name="rebuild"></a>**`REBUILD`**  
    Used to compact partitions and tables that have grown by multiple, incremental insertions into the same partitions in order to improve query performance over such tables.  If the table is empty or has only been loaded once, the operation will succeed without the need to perform a compaction.

-    <a name="add_drop"></a>**`ADD  | DROP`**  
    If an already existing column is attempted to be added or a non-existent column is attempted to be dropped, an error is raised.  
      
-    <a name="cdl"></a>**`Column_Definition_List`**       
The name(s) and built-in USQL type of the column(s) to be added.  If the added column is of a nullable type, existing rows will contain null in the added column.  If the added column is of a not-nullable type, then the column will contain the type's default value (e.g., 0 for type int).  

-    <a name="identList"></a>**`Identifier_List`**  
The name(s) of the column(s) to be dropped.  A column cannot be dropped when it is: 
     * Used in an index. 
     * Used in a partition.

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the table defintion below.   

**Test Table**   
```
CREATE DATABASE IF NOT EXISTS TestReferenceDB; 
USE DATABASE TestReferenceDB;

DROP TABLE IF EXISTS Logs;
CREATE TABLE Logs (
    date DateTime, 
    eventType int, 
    eventTime DateTime, 
    INDEX Index_EventType CLUSTERED (eventType ASC) 
    DISTRIBUTED BY HASH(eventType) INTO 3);
```

**Table Rebuild**   
```
//Introduce multiple incremental inserts
USE DATABASE TestReferenceDB;

INSERT INTO dbo.Logs
(date, eventType, eventTime)
VALUES
(new DateTime(2017,01,01), 1, new DateTime(2017,01,01,12,00,00));

INSERT INTO dbo.Logs
VALUES
(new DateTime(2017,02,01), 1, new DateTime(2017,02,01,12,00,00));

/*
// Rebuild table.  Execute separately and after INSERT statements above.
ALTER TABLE TestReferenceDB.dbo.Logs
REBUILD;
*/
```

**Various Column Scenarios**    
```
USE DATABASE TestReferenceDB;

// Add a column
ALTER TABLE Logs ADD COLUMN eventName string;

// add another column
ALTER TABLE Logs ADD COLUMN result int;

// drop a column and add another one
ALTER TABLE Logs DROP COLUMN result;
ALTER TABLE Logs ADD COLUMN clientId string;

// drop a column and add 3 more columns
ALTER TABLE Logs DROP COLUMN clientId;
ALTER TABLE Logs ADD COLUMN result string, clientId string, payload int?;

// drop 2 columns
ALTER TABLE Logs DROP COLUMN clientId, result;
```

### See Also  
* [CREATE TABLE (U-SQL): Creating a Table with Schema](create-table-u-sql-creating-a-table-with-schema.md)   
* [TRUNCATE TABLE (U-SQL)](truncate-table-u-sql.md)
* [DROP TABLE (U-SQL)](drop-table-u-sql.md)  