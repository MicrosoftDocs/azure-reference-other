---
title: "usql.indexes (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-09-26"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 4dcab57b-2e4e-4bdc-8766-8d31200f7367
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# usql.indexes (U-SQL)
Contains one row per index for the schemas of the current database context.

> [!NOTE]
> Some of the values documented below, such as the values for non-clustered indices and column-store indices, are there for possible future use and are not currently used.

Column name  |Data type  |Description  
---------|---------|---------
name     |string         |Name of the index        
object_id_guid     |Guid         |Identifier of the object on which the index is defined         
index_id     |int         |Ordinal position (starting at 1) of the index within the object/table         
type     |int         |Type of index:<br><br> 1 = Clustered<br><br>2 = Nonclustered<br><br>5 = Clustered Columnstore           
type_desc     |string         |Description of index type:<br><br> CLUSTERED<br><br>NONCLUSTERED<br><br> CLUSTERED COLUMNSTORE  

### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 

**Query the usql.indexes view**
```
USE TestReferenceDB;

OUTPUT usql.indexes
TO "/ReferenceGuide/CatalogViews/indexes.txt"
USING Outputters.Tsv(outputHeader:true);
```

**Query the usql.indexes view with usql.objects view**
```
@indexes =
    SELECT o.name AS objectName,
            i.*
    FROM usql.indexes AS i
    JOIN usql.objects AS o
    ON i.object_id_guid == o.object_id_guid;

OUTPUT @indexes
TO "/ReferenceGuide/CatalogViews/indexes_objects.txt"
USING Outputters.Tsv(outputHeader:true);  
```

### See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [usql.index_columns (U-SQL)](usql-index-columns-u-sql.md)
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)
