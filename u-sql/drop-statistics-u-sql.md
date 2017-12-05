---
title: "DROP STATISTICS (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 662259df-3b75-4ac2-95d4-ef330c4b1037
caps.latest.revision: 9
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# DROP STATISTICS (U-SQL)
U-SQL provides the `DROP STATISTICS` statement to drop the specified statistic of a table.  
  
Note that dropping statistics may have negative impact on the performance on queries over the associated table.  
  
> [!WARNING]
> **This operation cannot be undone!**

<table><th align="left">Syntax</th><tr><td><pre>
Drop_Statistics_Statement :=                                                                             
    'DROP' 'STATISTICS' [<a href="#IE">'IF' 'EXISTS'</a>]  
    <a href="#stat_name_tbl">Statistic_Name 'ON' Table_Name</a>.<br />
<a href="#stat_name_tbl">Statistic_Name</a> := 
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.<br />   
Table_Name := 
    <a href="u-sql-identifiers.md">Identifier</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements    
-   <a name="stat_name_tbl"></a>**`Statistic_Name ON Table_Name`**  
    Specifies the name (either a [quoted or unquoted identifier](u-sql-identifiers.md)) of the statistic of the given table to be dropped.  
  
-   <a name="IE"></a>**`IF EXISTS`**  
    If the statistic does not exist or the user does not have permissions, then an error is raised, unless `IF EXISTS` is specified. In that case, if the user has at least enumeration permission on the table, the operation will silently complete without action. If the user has no enumeration permission, an error is raised.  
  
### Example    
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

The following example drops the statistics, `ordersStats`, within the table `Orders` in `TestReferenceDB`.  
```
DROP STATISTICS IF EXISTS ordersStats ON TestReferenceDB.dbo.Orders;   
```
  
### See Also
-  [CREATE STATISTICS (U-SQL)](create-statistics-u-sql.md)
-  [UPDATE STATISTICS (U-SQL)](update-statistics-u-sql.md)
- [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)  
