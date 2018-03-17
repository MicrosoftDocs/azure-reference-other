---
title: "usql.views (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "09/26/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b601faa1-0741-410a-b51f-f36c1506fc2b
caps.latest.revision: 2
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# usql.views (U-SQL)
Returns a row for each view belonging to the schemas in the current database context. The schema inherits the columns from the [usql.objects](usql-objects-u-sql.md) view and adds the view specific properties to it.

Column name  |Data type  |Description  
---------|---------|---------
\<inherited columns>      |        |For a list of columns that this view inherits, see [usql.objects](usql-objects-u-sql.md).          
is_schema_inferred     |bool         |Indicates if the schema is inferred from the schema's query expression or has been explicitly provided         
definition     |string         |View's definition (if available)         

### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 


**Query the usql.views view**
```sql
USE TestReferenceDB;

OUTPUT usql.views
TO "/ReferenceGuide/CatalogViews/views.txt"
USING Outputters.Tsv(outputHeader:true);
```

**Query usql.views for multiple databases**
```sql
@views =
    SELECT "TestReferenceDB" AS db, * FROM TestReferenceDB.usql.views
    UNION ALL
    SELECT "master" AS db, * FROM master.usql.views;

OUTPUT @views
TO "/ReferenceGuide/CatalogViews/views_multiple.txt"
ORDER BY db
USING Outputters.Tsv(outputHeader:true);
```


### See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)



