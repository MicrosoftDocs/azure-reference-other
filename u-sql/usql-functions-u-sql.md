---
title: "usql.functions (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "09/26/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 103632cf-a0dc-43fb-9c25-6d3b7650ab78
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# usql.functions (U-SQL)
Contains one row per function belonging to the schemas in the current database context.

Column name  |Data type  |Description  
---------|---------|---------
\<inherited columns>      |         |For a list of columns that this view inherits, see [usql.objects](usql-objects-u-sql.md).       
is_user_defined     |bool         |Indicates if it is a user defined function         
definition     |string         | Function's definition (if available)         


### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 

**Query the usql.functions view**
```sql
USE TestReferenceDB;

OUTPUT usql.functions
TO "/ReferenceGuide/CatalogViews/functions.txt"
USING Outputters.Tsv(outputHeader:true);
```

### See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)
