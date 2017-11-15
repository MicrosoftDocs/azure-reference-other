---
title: "usql.partition_parameters (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-09-26"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b1496ee6-defd-478f-939f-06c2604533a3
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# usql.partition_parameters (U-SQL)
Provides details about the partition parameters for the partition schemes in the schemas of the current database context. The partitioned table must contain at least one record.

Column name  |Data type  |Description  
---------|---------|---------
object_id_guid     |Guid         |Identifier of the object on which the partition is specified.         
index_id     |int         |Identifier of the index for which the partition is specified.         
parameter_id     |int         |Ordinal position (starting at 1) of the parameter (unique within a partition scheme).         
column_id     |int         |Ordinal position of the column in the partition scheme         
 

### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 


**Query the usql.partitions view**
```
USE TestReferenceDB;

OUTPUT usql.partition_parameters
TO "/ReferenceGuide/CatalogViews/partition_parameters.txt"
USING Outputters.Tsv(outputHeader:true);
```

**Query the usql.partition_parameters view with other views**
```
@partition_parameters =
    SELECT o.name AS tableName,
            c.name AS columnName,
            p.partition_id_guid,
            pp.*
    FROM usql.partitions AS p
    JOIN usql.objects AS o
    ON p.object_id_guid == o.object_id_guid
    JOIN usql.partition_parameters AS pp
    ON p.object_id_guid == pp.object_id_guid
    JOIN usql.columns AS c
    ON o.object_id_guid == c.object_id_guid
    AND pp.column_id == c.column_id;

OUTPUT @partition_parameters
TO "/ReferenceGuide/CatalogViews/partition_parameters_others.txt"
USING Outputters.Tsv(outputHeader:true);  
```

### See Also
* [Catalog Views (U-SQL)](../u-sql/catalog-views-u-sql.md)
* [U-SQL Table Partitions and Distributions](../u-sql/create-table-u-sql-creating-a-table-with-schema.md#partitioning)
* [usql.partitions (U-SQL)](../u-sql/usql-partitions-u-sql.md)
* [usql.partition_range_values (U-SQL)](../u-sql/usql-partition-range-values-u-sql.md)
* [usql.objects (U-SQL)](../u-sql/usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](../u-sql/data-definition-language-ddl-statements-u-sql.md)


