---
title: "U-SQL Data Sources | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8e30a01e-a47e-4eed-ba3d-baddd9d4d99f
caps.latest.revision: 13
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# U-SQL Data Sources
One of the major value propositions of U-SQL is that it allows to query data where it lives. For external systems, such as Microsoft Azure SQL Database, this is achieved with [federated queries against data sources](u-sql-select-selecting-from-an-external-rowset.md).  
  
In order to query these external data sources, a data source object has to be created and referenced that abstracts the connection information as well as information about its capabilities to execute query expressions passed and translated from U-SQL to the its local query engine.  

### Data Source DDL Statements    
The following are the DDL statements that allow to manage data sources:

<table><th align="left">Syntax</th><tr><td><pre>
Datasource_DDL_Statement :=                                                                              
     <a href="create-data-source-u-sql.md">Create_Datasource_Statement</a>
|    <a href="alter-data-source-u-sql.md">Alter_Datasource_Statement</a>
|    <a href="drop-data-source-u-sql.md">Drop_Datasource_Statement</a>.
</pre></td></tr></table>

### See Also
* [CREATE DATA SOURCE (U-SQL)](create-data-source-u-sql.md)  
* [ALTER DATA SOURCE (U-SQL)](alter-data-source-u-sql.md)  
* [DROP DATA SOURCE (U-SQL)](drop-data-source-u-sql.md)  
