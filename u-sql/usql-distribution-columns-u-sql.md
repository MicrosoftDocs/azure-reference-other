---
title: "usql.distribution_columns (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-09-26"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e3967e8d-a1b8-4e00-ac59-ac2d19b835a2
caps.latest.revision: 3
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# usql.distribution_columns (U-SQL)
Returns the columns used by the distribution schemes for the tables in the schemas of the current database context.

Column name  |Data type  |Description  
---------|---------|---------
object_id_guid     |Guid         |Identifier of the object for which the distribution is specified         
index_id     |int?         |Identifier of the index for which the distribution is specified or `null` if it is specified directly on the table         
distribution_column_id     |int         |Ordinal position of the column in the distribution definition         
column_id     |int         |Position of the column within the object on which the statistics is specified (unique within object_id_guid)         
is_descending_key     |bool         |True = The distribution column has a descending sort direction<br><br> False = The distribution column has an ascending sort direction  


### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 

**Query the usql.distribution_columns view**
```
USE TestReferenceDB;

OUTPUT usql.distribution_columns
TO "/ReferenceGuide/CatalogViews/distribution_columns.txt"
USING Outputters.Tsv(outputHeader:true);
```

**Query the usql.distribution_columns view with usql.objects view**
```
@distribution_columns =
    SELECT o.name AS tableName,
            c.name AS columntName,
            dc.*
    FROM usql.objects AS o
    JOIN usql.distribution_columns AS dc
    ON o.object_id_guid == dc.object_id_guid
    JOIN usql.columns AS c
    ON dc.object_id_guid == c.object_id_guid
    AND dc.column_id == c.column_id;

OUTPUT @distribution_columns
TO "/ReferenceGuide/CatalogViews/distribution_columns_others.txt"
USING Outputters.Tsv(outputHeader:true);  
```

### See Also
* [Catalog Views (U-SQL)](../USQL/catalog-views-u-sql.md)
* [U-SQL Table Distributions ](../USQL/create-table-u-sql-creating-a-table-with-schema.md#dis_sch)
* [usql.distributions (U-SQL)](../USQL/usql-distributions-u-sql.md) 
* [usql.objects (U-SQL)](../USQL/usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](../USQL/data-definition-language-ddl-statements-u-sql.md)


