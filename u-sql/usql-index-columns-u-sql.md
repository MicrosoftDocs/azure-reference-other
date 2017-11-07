---
title: "usql.index_columns (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-09-26"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a32ac219-e2cd-46d2-b378-5c089c6ce139
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# usql.index_columns (U-SQL)
Contains one row per column for the indices of the schemas for the current database context.

> [!NOTE]
> Note that some of the values documented below, such as the values for non-clustered indices, column-store indices, or included columns, are there for possible future use and are not currently used.


Column name  |Data type  |Description  
---------|---------|---------
object_id_guid     |Guid         |Identifier of the object on which the index is defined         
index_id     |int         |Ordinal position (starting at 1) of the index within the object/table         
index_column_id      |int         |Position of the index column within the index (unique within the index_id)         
column_id     |int         |Position of the column within the object on which the index is specified (unique within object_id_guid) or 0 if it is the row identifier (RID) in a nonclustered index         
key_ordinal      |int         |Ordinal (1-based) within the set of key-columns<br><br> 0 = Not a key column, or it is a columnstore index
is_descending_key|bool|True = Index key column has a descending sort direction<br><br>False = Index key column has an ascending sort direction, or the column is part of a columnstore or hash index
is_included_column|bool|True = Column is a non-key column added to the index as an included column<br><br> False = Column is not an included column


### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 

**Query the usql.index_columns view**
```
USE TestReferenceDB;

OUTPUT usql.index_columns
TO "/ReferenceGuide/CatalogViews/index_columns.txt"
USING Outputters.Tsv(outputHeader:true);
```

**Query the usql.index_columns view with other catalog views**
```
@index_columns =
    SELECT i.name AS indexName,
            o.name AS objectName,
            c.name AS columnName,
           ic. *
    FROM usql.index_columns AS ic
    JOIN usql.indexes AS i
    ON ic.object_id_guid == i.object_id_guid
    JOIN usql.objects AS o
    ON i.object_id_guid == o.object_id_guid
    JOIN usql.columns AS c
    ON i.object_id_guid == c.object_id_guid
    AND ic.column_id == c.column_id;

OUTPUT @index_columns
TO "/ReferenceGuide/CatalogViews/index_columns_others.txt"
USING Outputters.Tsv(outputHeader:true); 
```

### See Also
* [Catalog Views (U-SQL)](../USQL/catalog-views-u-sql.md)
* [usql.indexes (U-SQL)](../USQL/usql-indexes-u-sql.md) 
* [usql.objects (U-SQL)](../USQL/usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](../USQL/data-definition-language-ddl-statements-u-sql.md)

