---
title: "usql.tables (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-09-26"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8d9d604e-d7f2-469b-8916-cd1919e5f633
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# usql.tables (U-SQL)

Returns a row for each table belonging to the schemas in the current database context. The schema inherits the columns from the [usql.objects](../USQL/usql-objects-u-sql.md) and adds the table specific properties to it.

Column name  |Data type  |Description  
---------|---------|---------
\<inherited columns>     |         |For a list of columns that this view inherits, see [usql.objects](../USQL/usql-objects-u-sql.md).         
is_external     |bool         |Indicates if this is an external table         
data_source_id_guid     |Guid?         |Data Source ID if the table is external, otherwise null         


### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 


**Query the usql.tables view**
```
USE TestReferenceDB;

OUTPUT usql.tables
TO "/ReferenceGuide/CatalogViews/tables.txt"
USING Outputters.Tsv(outputHeader:true);
```

**Query usql.tables for multiple databases**
```
@tables =
    SELECT "TestReferenceDB" AS db, * FROM TestReferenceDB.usql.tables
    UNION ALL
    SELECT "master" AS db, * FROM master.usql.tables;

OUTPUT @tables
TO "/ReferenceGuide/CatalogViews/tables_multiple.txt"
ORDER BY db
USING Outputters.Tsv(outputHeader:true);
```

### See Also
* [Catalog Views (U-SQL)](../USQL/catalog-views-u-sql.md)
* [usql.objects (U-SQL)](../USQL/usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](../USQL/data-definition-language-ddl-statements-u-sql.md)



