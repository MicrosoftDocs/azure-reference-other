---
title: "usql.partitions (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "09/26/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8cf9772d-d5e5-4346-902b-ddf7314c91f0
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# usql.partitions (U-SQL)
Contains one row per partition scheme for the partitioned tables in the schemas of the current database context.  The partitioned table must contain at least one record.

Column name  |Data type  |Description  
---------|---------|---------
partition_id_guid     |Guid         |Partition identifier         
object_id_guid     |Guid         |Identifier of the object on which the partition is specified.         
index_id     |int         | Identifier of the index for which the partition is specified.         


### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 


**Query the usql.partitions view**
```
USE TestReferenceDB;

OUTPUT usql.partitions
TO "/ReferenceGuide/CatalogViews/partitions.txt"
USING Outputters.Tsv(outputHeader:true);
```

**Query the usql.partitions view with other catalog views**
```
@partitions =
    SELECT o.name AS tableName,
            c.name AS columnName,
            p.*
    FROM usql.partitions AS p
    JOIN usql.objects AS o
    ON p.object_id_guid == o.object_id_guid
    JOIN usql.partition_parameters AS pp
    ON p.object_id_guid == pp.object_id_guid
    JOIN usql.columns AS c
    ON o.object_id_guid == c.object_id_guid
    AND pp.column_id == c.column_id;

OUTPUT @partitions
TO "/ReferenceGuide/CatalogViews/partitions_others.txt"
USING Outputters.Tsv(outputHeader:true);   
```

### See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [U-SQL Table Partitions and Distributions](create-table-u-sql-creating-a-table-with-schema.md#partitioning)
* [usql.partition_parameters (U-SQL)](usql-partition-parameters-u-sql.md)
* [usql.partition_range_values (U-SQL)](usql-partition-range-values-u-sql.md)
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)


