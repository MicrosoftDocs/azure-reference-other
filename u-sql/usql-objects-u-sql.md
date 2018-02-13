---
title: "usql.objects (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "09/26/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 469ae246-c58b-4ae6-bf7c-fea178803471
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# usql.objects (U-SQL)
Contains a row for certain schema-scoped objects that are created within a database.  Currently `usql.objects` only includes tables, views, table-valued functions and table types. Other objects such as procedures and packages will be added in the future.

Column name  |Data type  |Description  
---------|---------|---------
object_id_guid     |Guid         |Object's unique identifier         
name     |string         |Object's name (in simple, non-qualified form)         
schema_id_guid     |Guid         |Identifier of the schema that contains the object         
type     |string         |Object type:<br><br> TF = table-valued function<br><br> TT = table type<br><br> U = user table<br><br> V = view         
type_desc     |string         |Description of the object type:<br><br> TABLE_VALUED_FUNCTION<br><br> TABLE_TYPE<br><br> USER_TABLE<br><br> VIEW  
create_date|DateTime?|Date and time of the object's creation (in UTC-0 time zone)
modify_date|DateTime?|Date and time of the object's last modification (in UTC-0 time zone)

### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).

**Query the usql.objects view**
```sql
USE TestReferenceDB;

OUTPUT usql.objects
TO "/ReferenceGuide/CatalogViews/objects.txt"
USING Outputters.Tsv(outputHeader:true); 
```

### See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)





