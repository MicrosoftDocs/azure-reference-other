---
title: "CREATE STATISTICS (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 9e52b001-6176-4aab-9623-b29c03095392
caps.latest.revision: 11
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CREATE STATISTICS (U-SQL)
U-SQL provides the `CREATE STATISTICS` statement to create query optimization statistics on a column of a table.  
  
<table><th>Syntax</th><tr><td><pre>
Create_Statistics_Statement :=                                                                           
    'CREATE' 'STATISTICS' [<a href="#INE">'IF' 'NOT' 'EXISTS'</a>]  
    <a href="#stat_name">Statistic_Name</a>  
    'ON' <a href="#tabl_name">Table_Name</a> '(' <a href="#col_name">Column_Name</a> ')'  
    <a href="#w_flscn">'WITH' 'FULLSCAN</a>'.<br />
<a href="#stat_name">Statistic_Name</a> := 
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.<br /> 
<a href="#tabl_name">Table_Name</a> := 
    Identifier.<br />  
<a href="#col_name">Column_Name</a> := 
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements    
-   <a name="stat_name"></a>**`Statistic_Name`**    
    Specifies the name of the statistic as either a [quoted or unquoted identifier](u-sql-identifiers.md). The statistic name is unique in the context of the table, i.e., several tables could have statistics with the same name.  
  
-   <a name="INE"></a>**`IF NOT EXISTS`**     
    If the statistics of the given name already exists on the specified table and the user has access to it, an error is raised unless the `IF NOT EXISTS` clause has been specified. If the `IF NOT EXISTS` clause has been specified and the statistics already exists and the user has at least enumeration permissions, the `CREATE STATISTICS` statement will silently complete without action. If the user has no enumeration permission, an error is raised.  
  
-   <a name="tabl_name"></a>**`Table_Name`**  
    Specifies the table on which the statistic is being created. The table can be either specified with a fully qualified three-part name, a two-part name that refers to a table in the current database context, or a single name that refers to a table in the current database and schema context.  
  
    If the table does not exist or the user does not have permissions to create a statistic on it, an error is raised.  
  
-   <a name="col_name"></a>**`Column_Name`**  
    Specifies the column for which the statistics is being computed inside the parenthesis. Currently only one column can be specified. If the specified table or column does not exist or the user does not have access to it, an error is raised.  
  
-   <a name="w_flscn"></a>**`WITH FULLSCAN`**  
    The statistics are computed by scanning all rows. To provide compatibility with Microsoft SQL Server’s CREATE STATISTICS command, U-SQL currently requires the specification of `WITH FULLSCAN`.  
  
### Example    
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

The following example creates a statistics on the `OrderID` column within the table `Orders` in `TestReferenceDB`.  
  
```sql
USE TestReferenceDB; 
CREATE STATISTICS IF NOT EXISTS ordersStats ON dbo.Orders(OrderID) WITH FULLSCAN;  
```
  
### See Also
-  [UPDATE STATISTICS (U-SQL)](update-statistics-u-sql.md)
-  [DROP STATISTICS (U-SQL)](drop-statistics-u-sql.md)
- [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)  
 
