---
title: "usql.partition_range_values (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-09-26"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c58d8b96-c29f-40cf-9e58-b94ecf69cf70
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# usql.partition_range_values (U-SQL)
Provides details about the range partition schemes for the partitioned tables in the schemas of the current database context. The partitioned table must contain at least one record.

Column name  |Data type  |Description  
---------|---------|---------
partition_id_guid     |Guid         |Identifier of the range partition         
parameter_id     |int         |Ordinal position (starting at 1) of the parameter (unique within a partition scheme). Values in this column correspond to the parameter_id column of the `usql.partition_parameters` view for any particular partition_guid_id.         
value     |string         |Lexical representation of the value         


### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 

**Query the usql.partition_range_values view**
```
USE TestReferenceDB;

OUTPUT usql.partition_range_values
TO "/ReferenceGuide/CatalogViews/partition_range_values.txt"
USING Outputters.Tsv(outputHeader:true);
```

**Query the usql.partition_range_values view with other views**
```
@partition_range_values =
    SELECT o.name AS tableName,
            c.name AS columnName,
            prv.*
    FROM usql.partitions AS p
    JOIN usql.objects AS o
    ON p.object_id_guid == o.object_id_guid
    JOIN usql.partition_parameters AS pp
    ON p.object_id_guid == pp.object_id_guid
    JOIN usql.columns AS c
    ON o.object_id_guid == c.object_id_guid
    AND pp.column_id == c.column_id
    JOIN usql.partition_range_values AS prv
    ON p.partition_id_guid == prv.partition_id_guid;

OUTPUT @partition_range_values
TO "/ReferenceGuide/CatalogViews/partition_range_values_others.txt"
USING Outputters.Tsv(outputHeader:true);  
```


### See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [U-SQL Table Partitions and Distributions](create-table-u-sql-creating-a-table-with-schema.md#partitioning)
* [usql.partitions (U-SQL)](usql-partitions-u-sql.md)
* [usql.partition_parameters (U-SQL)](usql-partition-parameters-u-sql.md)
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)



