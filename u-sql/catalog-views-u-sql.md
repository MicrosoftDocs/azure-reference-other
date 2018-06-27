---
title: "Catalog Views (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "09/27/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: bf4a7487-fe80-4bba-bf1a-5c435f49e836
caps.latest.revision: 3
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# Catalog Views (U-SQL)
Catalog views return information that is used by U-SQL. We recommend that you use catalog views because they are the most general interface to the catalog metadata and provide the most efficient way to obtain, transform, and present customized forms of this information.

Catalog views will not contain objects that have been created as part of the same script and will only show the objects that the user submitting the query has the rights to see.

The U-SQL catalog views are currently not available in the local run environment.  Future releases will add additional catalog views.

The following catalog views are currently available:  

||  
|--|
| [usql.columns](usql-columns-u-sql.md)     |
| [usql.partition_parameters](usql-partition-parameters-u-sql.md)     |    
| [usql.databases](usql-databases-u-sql.md)     |
| [usql.partition_range_values](usql-partition-range-values-u-sql.md)  |       
| [usql.distributions](usql-distributions-u-sql.md)     |
| [usql.schemas](usql-schemas-u-sql.md)         |
| [usql.distribution_columns](usql-distribution-columns-u-sql.md)     |
| [usql.stats](usql-stats-u-sql.md)         |
| [usql.functions](usql-functions-u-sql.md)     |
| [usql.stats_columns](usql-stats-columns-u-sql.md)     |    
| [usql.indexes](usql-indexes-u-sql.md)     |
| [usql.tables](usql-tables-u-sql.md)       |  
| [usql.index_columns](usql-index-columns-u-sql.md)     |
| [usql.types](usql-types-u-sql.md)         |
| [usql.objects](usql-objects-u-sql.md)     | 
| [usql.views](usql-views-u-sql.md)        |
| [usql.partitions](usql-partitions-u-sql.md)|


## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  


**Query the usql.databases view**
```sql
USE TestReferenceDB;

OUTPUT usql.databases
TO "/ReferenceGuide/CatalogViews/databases.txt"
USING Outputters.Tsv(outputHeader:true);
```
<br />

**Querying multiple catalog views**  
The following script returns the tables with their fully qualified, quoted names as well as their column information (name and type and maximal possible field size) ordered alphabetically by table and in order of their column positions:
```sql
@result =
   SELECT "[" + db.name + "].[" + s.name + "].[" + t.name + "]" AS table_name,
          c.name AS col_name,
          c.column_id AS col_pos,
          ct.qualified_name AS col_type,
          c.max_length == - 1 ? 
            ct.qualified_name == "System.String" ? 
              128 * 1024 
            : ct.qualified_name == "System.Byte[]" ? 
                4 * 1024 * 1024 
              : - 1 
          : c.max_length AS col_max_length
   FROM usql.databases AS db 
   JOIN usql.schemas AS s ON db.database_id_guid == s.database_id_guid
   JOIN usql.tables AS t ON s.schema_id_guid == t.schema_id_guid
   JOIN usql.columns AS c ON c.object_id_guid == t.object_id_guid
   JOIN usql.types AS ct ON c.type_id_guid == ct.type_id_guid;

 OUTPUT @result
 TO "/ReferenceGuide/CatalogViews/tableinfo.csv"
 ORDER BY table_name, col_pos
 USING Outputters.Csv(outputHeader : true);
```
<br />

## See Also
* [U-SQL Concepts ](u-sql-concepts.md)   
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)

