---
title: "usql.distributions (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "09/26/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 9487d7ec-7a89-433c-9f52-b3d5e7707095
caps.latest.revision: 3
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# usql.distributions (U-SQL)
Contains one row per distribution scheme for the tables in the schemas of the current database context.

Column name  |Data type  |Description  
---------|---------|---------
object_id_guid     |Guid         |Identifier of the object for which the distribution is specified         
index_id     |int?         |Identifier of the index for which the distribution is specified or `null` if it is specified directly on the table.         
distribution_type     |int         |2 = Hash<br><br> 5 = Range<br><br> 6 = Round Robin<br><br> 17 = Direct Hash         
distribution_type_desc     |string         |HASH<br><br> RANGE<br><br> ROUND ROBIN<br><br> DIRECT HASH         
distribution_count     |int         |The specified count of distribution buckets if specified, null or 0 otherwise  

### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 

**Query the usql.distributions view**
```sql
USE TestReferenceDB;

OUTPUT usql.distributions
TO "/ReferenceGuide/CatalogViews/distributions.txt"
USING Outputters.Tsv(outputHeader:true);
```

**Query the usql.distributions view with usql.objects view**
```sql
@distributions =
    SELECT o.name AS objectName,
            d.*
    FROM usql.distributions AS d
    JOIN usql.objects AS o
    ON d.object_id_guid == o.object_id_guid;

OUTPUT @objects
TO "/ReferenceGuide/CatalogViews/distributions_objects.txt"
USING Outputters.Tsv(outputHeader:true);  
```

### See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [U-SQL Table Distributions ](create-table-u-sql-creating-a-table-with-schema.md#dis_sch)
* [usql.distribution_columns (U-SQL)](usql-distribution-columns-u-sql.md)
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)
