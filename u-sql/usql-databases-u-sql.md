---
title: "usql.databases  (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-09-26"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 1669a36f-277e-4dd6-836f-7cab58821d81
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# usql.databases  (U-SQL)
Contains one row per database belonging to the account's catalog.

Column name  |Data type  |Description  
---------|---------|---------
database_id_guid     |Guid         |Database's unique identifier (unique within an account)         
name     |string         |Database name (unique within an account)         
create_date     |DateTime?         |Date and time when the database was created (in UTC-0 time zone). Value may be null for databases that were created before the system started to track this information.  


### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  


**Query the usql.databases view**   
```
OUTPUT usql.databases
TO "/ReferenceGuide/CatalogViews/databases.txt"
USING Outputters.Tsv(outputHeader:true);
```

### See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)
