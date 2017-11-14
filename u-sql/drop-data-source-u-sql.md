---
title: "DROP DATA SOURCE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-13"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 719b1e5b-b2ec-4e0b-bafc-6a0581fda7ad
caps.latest.revision: 9
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# DROP DATA SOURCE (U-SQL)
A data source can be dropped with the `DROP DATA SOURCE` statement.  
  
> [!WARNING]
> **This operation cannot be undone!**

<table><th>Syntax</th><tr><td><pre>
Drop_Datasource_Statement :=                                                                             
    'DROP' 'DATA' 'SOURCE' [<a href="#IE">'IF' 'EXISTS'</a>] <a href="#dsrc_name">Datasource_Name</a>.
<br />
<a href="#dsrc_name">Datasource_Name</a> := 
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre></td></tr></table> 
  
### Semantics of Syntax Elements  
-   <a name="dsrc_name"></a>**`Datasource_Name`**   
Specifies the data source to be dropped in the current static database context. If a data source of the given name does not exist, or the user has no permissions to drop the data source, an error is raised.  
  
-   <a name="IE"></a>**`IF EXISTS`**   
If the optional `IF EXISTS` is specified, then the statement drops the data source if it already exists, or succeeds without changes if the data source does not exist or the user has no permission to at least enumerate all existing data sources.  
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  

```
USE TestReferenceDB;
DROP DATA SOURCE IF EXISTS MyAzureSQLDBDataSource;

DROP DATA SOURCE IF EXISTS MyAzureSQLDWDataSource;

DROP DATA SOURCE IF EXISTS MySQLServerDataSource;
```

### See Also
* [U-SQL Data Sources](u-sql-data-sources.md)  
* [CREATE DATA SOURCE (U-SQL)](create-data-source-u-sql.md)  
* [ALTER DATA SOURCE (U-SQL)](alter-data-source-u-sql.md)  

