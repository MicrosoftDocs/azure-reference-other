---
title: "UPDATE STATISTICS (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 2b497c88-fce4-4e12-910b-8051306f434e
caps.latest.revision: 14
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# UPDATE STATISTICS (U-SQL)
U-SQL provides the `UPDATE STATISTICS` statement to update a previously created statistic on a table.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Update_Statistics_Statement :=                                                                           
     'UPDATE' 'STATISTICS' ['IF' 'EXISTS']
     <a href="#stat_name_tbl">Statistic_Name 'ON' Table_Name</a>
     <a href="#incrm">'WITH' 'INCREMENTAL' '=' ('ON' | 'OFF')</a>.<br />
<a href="#stat_name_tbl">Statistic_Name</a> :=
     <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.<br />
Table_Name := 
     <a href="u-sql-identifiers.md">Identifier</a>.
</pre></td></tr></table>
 
### Semantics of Syntax Elements    
-   <a name="stat_name_tbl"></a>**`Statistic_Name ON Table_Name`**  
    Specifies the name (either a [quoted or unquoted identifier](../USQL/u-sql-identifiers.md)) of the statistic of the given table to be updated. If the statistic does not exist or the user does not have permissions, then an error is raised, unless `IF EXISTS` is specified. In that case, if the user has at least enumeration permission on the table, the operation will silently complete without action. If the user has no enumeration permission, an error is raised.  
  
-   <a name="incrm"></a>**`WITH INCREMENTAL = 'ON' | 'OFF'`**  
    When the `INCREMENTAL` option is set to `ON`, the statistics are updated with the newly inserted data and newly added partitions since the last time the statistic got calculated. If it is set to **`OFF`**, the statistics tree is dropped and the full statistic is recomputed.  
  
### Example    
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

The following example does a full update of the statistics, `ordersStats`,  within the table `Orders` in `TestReferenceDB`.  
  
```
USE TestReferenceDB;

UPDATE STATISTICS IF EXISTS ordersStats 
ON dbo.Orders
WITH INCREMENTAL = OFF;
```
### See Also
-  [CREATE INDEX (U-SQL)](../USQL/create-index-u-sql.md)
-  [DROP TABLE (U-SQL)](../USQL/drop-table-u-sql.md) 
-  [CREATE STATISTICS (U-SQL)](../USQL/create-statistics-u-sql.md)
-  [DROP STATISTICS (U-SQL)](../USQL/drop-statistics-u-sql.md)
- [Data Definition Language (DDL) Statements (U-SQL)](../USQL/data-definition-language-ddl-statements-u-sql.md)  
