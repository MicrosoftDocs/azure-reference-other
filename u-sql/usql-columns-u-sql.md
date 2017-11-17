---
title: "usql.columns (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-09-26"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 432cff25-ab72-40bb-af22-94e0ee3a8176
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# usql.columns (U-SQL)
Returns a row for each column in tables and table types in the schemas of the current database context.


Column name  |Data type  |Description  
---------|---------|---------
name     | string         |Column's name (unique within the object to which the column belongs)        
object_id_guid     |Guid         |Identifier of the object to which the columns belongs         
column_id     |int         |Column's positional id within the object to which the column belongs (unique within the object)         
type_id_guid     |Guid         |Column type's identifier.<br><br>  To return the name of the type, join to the [usql.types](usql-types-u-sql.md) catalog view on this column.       
max_length     |int?         |Column's maximum length in bytes.<br><br>  -1 = Variable sized column such as columns of type string or byte[] or of a [complex type](complex-built-in-u-sql-types.md). The value `null` is reserved for future use.         


### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 

**Query the usql.columns view**
```
USE TestReferenceDB;

OUTPUT usql.columns
TO "/ReferenceGuide/CatalogViews/columns.txt"
USING Outputters.Tsv(outputHeader:true);
```

**Query the usql.columns view with other catalog views**
```
@columns =
    SELECT "object" AS object_type,
            o.name AS objectName,
            c.*
    FROM usql.columns AS c
    JOIN usql.objects AS o
    ON c.object_id_guid == o.object_id_guid

    UNION ALL

    SELECT  "type" AS object_type,
            t.name AS objectName,
            c.*
    FROM usql.columns AS c
    JOIN usql.types AS t
    ON c.object_id_guid == t.type_id_guid;

OUTPUT @columns
TO "/ReferenceGuide/CatalogViews/columns_objects_types.txt"
ORDER BY object_type, objectName, name
USING Outputters.Tsv(outputHeader:true);  
```

### See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)
