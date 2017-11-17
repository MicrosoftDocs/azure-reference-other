---
title: "usql.stats (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-05"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8b817d79-fc2f-44b7-b3c2-315dcf29053c
caps.latest.revision: 3
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# usql.stats (U-SQL)
Contains a row for each statistics object that exists for the tables in the current database context.

The catalog view [usql.stats_columns](usql-stats-columns-u-sql.md) provides statistics information for each column in the database.  For more information about statistics, see [U-SQL Statistics](u-sql-statistics.md). 

Column name  |Data type  |Description  
---------|---------|---------
object_id_guid     |Guid         |Identifier of the object on which the statistics is defined         
name     |string         |Name of the statistics, unique for the object on which the statistics is defined         
stats_id_guid     |Guid         |Identifier of the statistics (unique within the object)         
create_date     |DateTime?         |Date of creation of the statistics. Some older statistics may have a value of null if they were created before the date was being recorded.         
update_date     |DateTime?         |Last update date of the statistics. Some older statistics may have a value of null if they were updated before the date was being recorded.
stat_data_byte|byte[]|Content of the statistics.  **CAUTION: This column may be subject to change in a future refresh!**  

### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 


**Query the usql.stats view**
```
USE TestReferenceDB;

OUTPUT usql.stats 
TO "/ReferenceGuide/CatalogViews/stats.txt"
USING Outputters.Tsv(outputHeader:true);
```

**Query the usql.stats view with usql.objects view**
```
@stats =
    SELECT o.name AS objectName,
            s.*
    FROM usql.stats AS s
    JOIN usql.objects AS o
    ON s.object_id_guid == o.object_id_guid;

OUTPUT @stats
TO "/ReferenceGuide/CatalogViews/stats_objects.txt"
USING Outputters.Tsv(outputHeader:true);  
```

### See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [usql.stats_columns (U-SQL)](usql-stats-columns-u-sql.md)
* [U-SQL Statistics](u-sql-statistics.md)
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)



