---
title: "usql.schemas (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "09/26/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6b54834f-fa91-4463-ac6d-2f0783de1aa0
caps.latest.revision: 2
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# usql.schemas (U-SQL)
Contains a row for each database schema in the current database context.

Column name  |Data type  |Description  
---------|---------|---------
schema_id_guid     |Guid         |Schema's unique identifier (unique within a database)         
name     |string         |Schema name (unique within a database)         
database_id_guid     |Guid         |Identifier of the database that contains the schema

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  


 **Query the usql.schemas view**
```sql
USE TestReferenceDB;

OUTPUT usql.schemas
TO "/ReferenceGuide/CatalogViews/schemas.txt"
USING Outputters.Tsv(outputHeader:true);
```
<br />

**Query the usql.schemas view with usql.databases view**
```sql
@schemas =
    SELECT d.name AS dbName,
            s.*
    FROM usql.schemas AS s
    JOIN usql.databases AS d
    ON s.database_id_guid == d.database_id_guid;

OUTPUT @schemas
TO "/ReferenceGuide/CatalogViews/schemas_databases.txt"
USING Outputters.Tsv(outputHeader:true);  
```

## See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)
