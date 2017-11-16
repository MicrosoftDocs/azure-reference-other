---
title: "USE DATABASE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c72a4568-4d10-4cc5-bf8f-18685f5dbd1b
caps.latest.revision: 17
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# USE DATABASE (U-SQL)
In order to simplify using names of objects in other databases than the default context database, U-SQL provides the ability to set a different database as the context database with the USE DATABASE statement. This sets the specified database as the new context database for all metadata object names in the remainder of the script until it gets changed with another `USE` statement. It also automatically sets the schema context to the database’s dbo schema. Therefore all names that are not fully qualified will be resolved with respect to the new context.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Use_Database_Statement :=                                                                                
     'USE' ['DATABASE'] <a href="#DB_Name">DB_Name</a>.<br />
<a href="#DB_Name">DB_Name</a> :=                                               
     <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre></td></tr></table>
  
The keyword `DATABASE` is optional to provide familiarity to T-SQL users.  
  
### Semantics of Syntax Elements    
-   <a name="DB_Name"></a>**`DB_Name`**    
    Specifies the name of the database in form of a [quoted or unquoted U-SQL identifier](u-sql-identifiers.md). If the database does not exist or the user has no permissions to at least enumerate the database, an error is raised.  
  
### Example  
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
  
The following script shows how using a database, `TestReferenceDB`, will allow the subsequent [`SELECT`](select-clause-u-sql.md) and [`DROP TABLE`](drop-table-u-sql.md) statements to operate on a table, `SampleTable`, within the `TestReferenceDB's` default schema context.  
```
USE DATABASE TestReferenceDB;  
@r = 
    SELECT * FROM SampleTable;  
    DROP TABLE SampleTable;  
    OUTPUT @r TO "output.txt" USING Outputters.Csv();
```
This script is equivalent to the following script that uses fully qualified names without setting the database context:  
```
@r = 
    SELECT * FROM TestReferenceDB.dbo.SampleTable;  
    DROP TABLE TestReferenceDB.dbo.SampleTable;  
    OUTPUT @r TO "output.txt" USING Outputters.Csv();
```
### See Also    
* [U-SQL Databases](u-sql-databases.md)  
* [CREATE DATABASE (U-SQL)](create-database-u-sql.md) 
* [DROP DATABASE (U-SQL)](drop-database-u-sql.md)
* [USE (U-SQL)](u-sql-metadata-object-naming-and-name-contexts.md)
