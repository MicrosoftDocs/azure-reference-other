---
title: "USE SCHEMA (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ccef2923-23a6-4e7a-9b46-17c176f1b3ef
caps.latest.revision: 12
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# USE SCHEMA (U-SQL)
In order to simplify using names of objects in other schemas than the default context schema in a script, U-SQL provides the ability to set a different schema as the context schema with the `USE SCHEMA` statement.  
  
The statement sets the specified schema as the new context schema (within the existing context database) for all metadata object names in the remainder of the script until it gets changed with another [`USE`](u-sql-metadata-object-naming-and-name-contexts.md) statement. All names that are not fully qualified will be resolved with respect to the new context.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Use_Schema_Statement :=                                                                                  
     'USE' 'SCHEMA' <a href="#s_name">Schema_Name</a>.<br />
<a href="#s_name">Schema_Name</a> :=  
     <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements    
-   <a name="s_name"></a>**`Schema_Name`**  
    Specifies the name of the schema in form of a [quoted or unquoted U-SQL identifier](u-sql-identifiers.md). If the schema does not exist in the current database context or the user has no permissions to at least enumerate the schema, an error is raised.  
  
### Examples  
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

The following script shows how using a schema `My Schema` within the current database context will allow the subsequent [SELECT](select-expression-u-sql.md) and [DROP](drop-table-u-sql.md) statements to operate on a table `SampleTable` within the `My Schema` schema.  
```  
USE SCHEMA [My Schema];  
@r = 
    SELECT * FROM SampleTable;  
    DROP TABLE SampleTable;  
    OUTPUT @r TO "output.txt" USING Outputters.Csv();  
```  
This script is equivalent to the following script that uses two-parts names to refer to the table in the current database context without setting the schema context:  
```  
@r = 
    SELECT * FROM [My Schema].SampleTable;  
    DROP TABLE [My Schema].SampleTable;  
    OUTPUT @r TO "output.txt" USING Outputters.Csv();  
```
  
### See Also    
* [U-SQL Database Schemas](u-sql-database-schemas.md)
* [CREATE SCHEMA (U-SQL)](create-schema-u-sql.md)
* [DROP SCHEMA (U-SQL)](drop-schema-u-sql.md)
* [USE (U-SQL)](u-sql-metadata-object-naming-and-name-contexts.md)
