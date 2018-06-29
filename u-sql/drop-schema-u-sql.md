---
title: "DROP SCHEMA (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 9ea54988-bf17-4032-80f6-9bb87fcb4e0d
caps.latest.revision: 9
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# DROP SCHEMA (U-SQL)
The statement drops the schema in the current database context and deletes all the data contained within from the system.  
  
> [!WARNING]   
> **This operation cannot be undone!**
  
## Syntax
<pre>
Drop_Schema_Statement :=  
    'DROP' 'SCHEMA' [<a href="#if_E">'IF' 'EXISTS'</a>] <a href="#s_name">Schema_Name</a>.<br />
<a href="#s_name">Schema_Name</a> :=  
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre>
  
## Semantics of Syntax Elements    
-   <a name="s_name"></a>**`Schema_Name`**   
    Specifies the name of the schema in form of a [quoted or unquoted U-SQL identifier](u-sql-identifiers.md). If a schema of the given name does not exist in the current database context, or the user has no permissions to drop a schema, an error is raised.  
    
-   <a name="if_E"></a>**`IF EXISTS`**  
    If the optional `IF EXISTS` is specified, then the statement drops the schema if it already exists, or succeeds without changes if the schema does not exist or the user has no permission to at least enumerate all existing schemas.  
  
## Example    
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


The following script shows how the `My Schema` schema is deleted from the current database context if it already exists before it is recreated:  
```sql  
DROP SCHEMA IF EXISTS [My Schema];  
CREATE SCHEMA [My Schema];  
```  

## See Also    
* [U-SQL Database Schemas](u-sql-database-schemas.md)
* [CREATE SCHEMA (U-SQL)](create-schema-u-sql.md)
* [USE SCHEMA (U-SQL)](use-schema-u-sql.md) 
* [Securing Meta Data Objects](securing-meta-data-objects.md)
