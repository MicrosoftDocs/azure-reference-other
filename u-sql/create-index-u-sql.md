---
title: "CREATE INDEX (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 2430396f-e5c8-4d7f-96aa-910be80d9c31
caps.latest.revision: 20
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CREATE INDEX (U-SQL)
This statement creates a clustered index with the given name on the specified table.

<table><th align="left">Syntax</th><tr><td><pre>
Create_Index_Statement :=                                                                                
     'CREATE' 'CLUSTERED' 'INDEX' <a href="#QUI">Quoted_or_Unquoted_Identifier</a>
     'ON' <a href="#Ident">Identifier</a> '(' <a href="#sil">Sort_Item_List</a> ')' [<a href="#PS">Partition_Specification</a>].
</pre></td></tr></table>

### Semantics of Syntax Elements    
-   <a name="QUI"></a>**`Quoted_or_Unquoted_Identifier`**   
    Specifies the name of the index as either a quoted or unquoted identifier. The index name is unique in the context of the table, i.e., several tables could have indexes with the same name.  
  
-   <a name="Ident"></a>**`Identifier`**   
    The table can be either specified with a fully qualified three-part name, a two-part name that refers to a table in the current database context, or a single name that refers to a table in the current database and schema context.  
  
    If the table does not exist or the user does not have permissions to create an index on it, an error is raised. An error is also raised if the table already has a clustered index specified, since every table can only have one clustered index.  
  
-   <a name="sil"></a>**`Sort_Item_List`**   
    Specifies the column names and optional sort order that is used to perform the clustering of the data.  
  
-   <a name="PS"></a>**`Partition_Specification`**   
    The optional [partition specification](create-table-u-sql-creating-a-table-with-schema.md#partition_spec) specifies how the index (and thus the table) will be partitioned. 
  
Note that it is normally recommended to define the clustered index with the [CREATE TABLE](u-sql-tables.md) statement. While the index definition is optional as part of the table definition, no data can be inserted into the table until an index has been defined.  

### Example    
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

The following example creates a Clustered Index on the columns `OrderID` and `CustomerID` on an existing table called `Orders` in `TestReferenceDB`.  `Orders` will also be partitioned on column `OrderDate`.  The example provides an alternative for the same table created in  the example for [CREATE TABLE (U-SQL): Creating a Table with Schema](create-table-u-sql-creating-a-table-with-schema.md).
```sql  
CREATE DATABASE IF NOT EXISTS TestReferenceDB;
USE TestReferenceDB;

DROP TABLE IF EXISTS dbo.Orders;
CREATE TABLE dbo.Orders
(
    OrderID int,
    CustomerID int,
    OrderDetailID int,
    OrderTotal double,
    OrderDate DateTime
);

CREATE CLUSTERED INDEX clx_OrderID_CustomerID 
ON TestReferenceDB.dbo.Orders(OrderID, CustomerID ASC)
PARTITIONED BY (OrderDate)
DISTRIBUTED BY HASH (OrderID, CustomerID);
```  

### See Also    
* [DROP INDEX (U-SQL)](drop-index-u-sql.md)
* [CREATE TABLE (U-SQL): Creating a Table with Schema](create-table-u-sql-creating-a-table-with-schema.md)    
* [CREATE TABLE (U-SQL): Creating a Table from a Query](create-table-u-sql-creating-a-table-from-a-query.md)  
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)

 
