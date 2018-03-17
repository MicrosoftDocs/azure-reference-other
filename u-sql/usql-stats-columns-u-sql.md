---
title: "usql.stats_columns (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "09/26/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 3e454008-66bf-441a-b78c-49ed6abb1216
caps.latest.revision: 2
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# usql.stats_columns (U-SQL)

Contains a row for each column that is part of [usql.stats](usql-stats-u-sql.md) statistics. 

Column name  |Data type  |Description  
---------|---------|---------
object_id_guid     |Guid         |Identifier of the object on which the statistics is defined         
stats_id_guid     |Guid         |Identifier of the statistics of which the column is part         
stats_column_id     |int         |Ordinal position (starting at 1) of the column within the list of statistics columns         
column_id     |int         |Position of the column within the object on which the statistics is specified (unique within object_id_guid)         


### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 


**Query the usql.stats_columns view**
```sql
USE TestReferenceDB;

OUTPUT usql.stats_columns 
TO "/ReferenceGuide/CatalogViews/stats_columns.txt"
USING Outputters.Tsv(outputHeader:true);
```

**Query the usql.stats_columns view with other catalog views**
```sql
@stats_columns =
    SELECT o.name AS objectName,
            s.name AS statName,
            c.name AS columnName,
            sc.*
    FROM usql.objects AS o
    JOIN usql.stats AS s
    ON o.object_id_guid == s.object_id_guid
    JOIN usql.stats_columns AS sc
    ON s.object_id_guid == sc.object_id_guid
    JOIN usql.columns AS c
    ON sc.object_id_guid == c.object_id_guid
    AND sc.column_id == c.column_id;

OUTPUT @stats_columns
TO "/ReferenceGuide/CatalogViews/stats_columns_others.txt"
USING Outputters.Tsv(outputHeader:true);  
```

### See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [usql.stats (U-SQL)](usql-stats-u-sql.md)
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)



