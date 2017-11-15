---
title: "DROP DATABASE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 577f9869-f215-4687-ac8a-2d0e1246ab45
caps.latest.revision: 15
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# DROP DATABASE (U-SQL)
The statement drops the database and deletes all the data contained within from the system. If a database of the given name does not exist, or the user has no permissions to drop a database, an error is raised.  
  
> [!WARNING]
> **This operation cannot be undone!**
  
<table><th align="left">Syntax</th><tr><td><pre>
Drop_Database_Statement :=                                                                               
    'DROP' 'DATABASE' [<a href="#iff_e">'IF' 'EXISTS'</a>] <a href="#DB_Name">DB_Name</a>.<br />
<a href="#DB_Name">DB_Name</a> :=  
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre></td></tr></table>
  
### Semantics of Syntax Elements  
-   <a name="DB_Name"></a>**`DB_Name`**   
    Specifies the name of the database to be dropped in form of a [quoted or unquoted U-SQL identifier](u-sql-identifiers.md). If a database of the given name does not exist or the user has no permissions to drop a database, an error is raised.   
  
-   <a name="iff_e"></a>**`IF EXISTS`**   
    If the optional `IF EXISTS` is specified, then the statement drops the database if it already exists, or succeeds without changes if the database does not exist or the user has no permission to at least enumerate all existing databases.  
  
### Example    
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

The following script shows how the `TestReferenceDB` database is deleted if it already exists before it is recreated:  
```
DROP DATABASE TestReferenceDB; 

// with IF  EXISTS
DROP DATABASE IF EXISTS TestReferenceDB; 
```
  
### See Also    
* [U-SQL Databases](u-sql-databases.md)  
* [CREATE DATABASE (U-SQL)](create-database-u-sql.md)
* [USE DATABASE (U-SQL)](use-database-u-sql.md)
