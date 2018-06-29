---
title: "CREATE SCHEMA (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6d6af34b-5595-4870-bfb2-3e70c49dc8c5
caps.latest.revision: 8
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# CREATE SCHEMA (U-SQL)
This statement creates a new schema with the specified name in the current database context. 
  
## Syntax
<pre>
Create_Schema_Statement := 
    'CREATE' 'SCHEMA' [<a href="#INE">'IF' 'NOT' 'EXISTS'</a>] <a href="#s_name">Schema_Name</a>.<br />
<a href="#s_name">Schema_Name</a> :=  
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre>

## Semantics of Syntax Elements  
- <a name="s_name"></a>**`Schema_Name`**   
Specifies the name of the schema in form of a [quoted or unquoted U-SQL identifier](u-sql-identifiers.md). If a schema of the given name already exists inside the current database context or the user has no permissions to create a schema, an error is raised. 
     
- <a name="INE"></a>**`IF NOT EXISTS`**  
If the optional `IF NOT EXISTS` is specified, then the statement creates the schema if it does not already exist, or succeeds without changes if the schema already exists and the user has permission to at least enumerate all existing schemas.  
  
## Examples    
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Basic Syntax**   
The following script shows how a user creates a schema called `My Schema`. Note that because of the space in the name, the identifier has to be quoted:  
```sql
CREATE SCHEMA [My Schema];
```
<br />

**Additional Example**  
If the user wants to create a schema in another database than the current database context, then the database context has to be changed explicitly. In the following example, a new database `TestReferenceDB` gets created that contains a new schema called `NewSchema` in addition to the automatically created `dbo` schema:  
```sql
CREATE DATABASE TestReferenceDB;  
USE DATABASE TestReferenceDB;  
CREATE SCHEMA NewSchema;
```

## See Also    
* [U-SQL Database Schemas](u-sql-database-schemas.md)
* [USE SCHEMA (U-SQL)](use-schema-u-sql.md) 
* [DROP SCHEMA (U-SQL)](drop-schema-u-sql.md)
* [Securing Meta Data Objects](securing-meta-data-objects.md)
