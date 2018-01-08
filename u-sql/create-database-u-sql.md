---
title: "CREATE DATABASE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e3ddc453-fd1f-42b8-bc49-981ddc44d10c
caps.latest.revision: 14
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CREATE DATABASE (U-SQL)
This statement creates a new U-SQL database with the specified name.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Create_Database_Statement :=                                                                             
    'CREATE' 'DATABASE' [<a href="#INE">'IF' 'NOT' 'EXISTS'</a>] <a href="#DB_Name">DB_Name</a>.<br />
<a href="#DB_Name">DB_Name</a> :=  
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre></td></tr></table>
  
### Semantics of Syntax Elements    
-   <a name="DB_Name"></a>**`DB_Name`**  
    Specifies the name of the database in form of a [quoted or unquoted U-SQL identifier](u-sql-identifiers.md). If a database of the given name already exists or the user has no permissions to create a database, an error is raised.    
   
-   <a name="INE"></a>**`IF NOT EXISTS`**  
    If the optional `IF NOT EXISTS` is specified, then the statement creates the database if it does not already exist, or succeeds without changes if the database already exists and the user has permission to at least enumerate all existing databases.  
  
### Example   
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
 
The following script shows how a user created a database called `TestReferenceDB`:  
```
CREATE DATABASE TestReferenceDB; 

// with IF NOT EXISTS
CREATE DATABASE IF NOT EXISTS TestReferenceDB; 
```
### See Also    
* [U-SQL Databases](u-sql-databases.md)  
* [USE DATABASE (U-SQL)](use-database-u-sql.md)  
* [DROP DATABASE (U-SQL)](drop-database-u-sql.md)
