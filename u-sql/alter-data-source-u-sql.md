---
title: "ALTER DATA SOURCE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-13"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6827d5ef-71ca-4231-a81c-55ec02d0014d
caps.latest.revision: 7
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# ALTER DATA SOURCE (U-SQL)
The `ALTER DATA SOURCE` statement allows to change an existing data source.  
  
<table><th>Syntax</th><tr><td><pre>
Alter_Datasource_Statement :=                                                                            
    'ALTER' 'DATA' 'SOURCE' <a href="#dsrc_name">Datasource_Name</a>   
    'SET' <a href="#dsrc_opt">Datasource_Options</a>.
<br />
<a href="#dsrc_name">Datasource_Name</a> := 
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
<br />
<a href="#dsrc_opt">Datasource_Options</a> :=  
    Datasource_Option {',' Datasource_Option}.
</pre></td></tr></table>
  
### Semantics of Syntax Elements    
-   <a name="dsrc_name"></a>**`Datasource_Name`**   
Specifies the name of the data source to be altered in the current static database context. If a data source of the given name does not exist in the database context or the user has no permissions to alter the data source, an error is raised.  
  
-   <a name="dsrc_opt"></a>**`Datasource_Options`**   
Specifies the options that are being changed. The options provide the information on how to connect and interact with the external data source. These options are source specific (although at the moment they all apply to the three supported sources). See [CREATE DATA SOURCE (U-SQL)](create-data-source-u-sql.md) for a list of supported data source options and their semantics.  
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  

```
USE DATABASE TestReferenceDB;

ALTER DATA SOURCE MySQLServerDataSource
SET
    PROVIDER_STRING = "Database=Sales";
```
  
### See Also
* [U-SQL Data Sources](u-sql-data-sources.md)  
* [CREATE DATA SOURCE (U-SQL)](create-data-source-u-sql.md)  
* [DROP DATA SOURCE (U-SQL)](drop-data-source-u-sql.md)  




  