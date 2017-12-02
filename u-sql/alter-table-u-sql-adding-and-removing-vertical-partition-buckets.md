---
title: "ALTER TABLE (U-SQL): Adding and Removing Vertical Partition Buckets | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-28"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c3bebe09-672b-43b1-9e4f-2a469b9b9e8e
caps.latest.revision: 19
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# ALTER TABLE (U-SQL): Adding and Removing Vertical Partition Buckets
In order to add or remove vertical partition buckets from a partitioned table, U-SQL provides the following `ALTER TABLE` statements.  
  
If the partition buckets are dropped, then the data contained in the partitions will be deleted.   
  
If the partition buckets are added, then the data has to be inserted into the buckets with either implicit or explicit inserts into the buckets.  

<table><th align="left">Syntax</th><tr><td><pre>
Alter_Table_AddDrop_Partition_Statement :=                                                               
    'ALTER' 'TABLE' <a href="#ident">Identifier</a>   
    ( '<a href="#add_drop">ADD</a>' ['IF' 'NOT' 'EXISTS']   
    | '<a href="#add_drop">DROP</a>' ['IF' 'EXISTS'] )  
    <a href="#partition_label_list">Partition_Label_List</a>.</pre></td></tr></table>

### Semantics of Syntax Elements  
-    <a name="ident"></a>**`Identifier`**   
Identifies the table to be changed. If the Identifier is a three-part identifier, the table from the specified database and schema will be chosen. If the Identifier is a two-part identifier, then the table of the given schema and of the given name of the current static database context is chosen. If the identifier is a simple identifier, then the table of the given name in the current static database and schema context is chosen.  
    
        If the table does not exist, is an external table, or the user does not have permissions to add or remove partition buckets to the table, an error is raised.  
  
-    <a name="add_drop"></a>**`ADD [IF NOT EXISTS] | DROP [IF EXISTS]`**  
    If an already existing partition bucket is added or a non-existent partition bucket is attempted to be dropped, an error is raised unless the `IF NOT EXISTS` or `IF EXISTS` clause is specified respectively.  
  
- <a name="partition_label_list"></a>**`Partition_Label_List`**  
The partition label list specifies the list of partition buckets to be added or deleted by specifying the literal values for the partition columns using the appropriate types. The values have to be provided as constants or as scalar static variables.
<table><th>Syntax</th><tr><td><pre>
Partition_Label_List :=                                                                             
    Partition_Label {',' Partition_Label}.<br />  
Partition_Label :=                                                              
    'PARTITION' Static_Expression_Row_Constructor.<br />  
Static_Expression_Row_Constructor := 
    '(' Static_Expression_List ')'.<br />      
Static_Expression_List := 
    Static_Expression {',' Static_Expression}.<br />  
Static_Expression := 
    <a href="textual-types-and-literals.md">string_literal</a> | <a href="numeric-types-and-literals.md">number_literal</a> | <a href="textual-types-and-literals.md">char_literal</a> | Static_Variable | binary_literal.
</pre></td></tr></table> 
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the table defined below.  

```
CREATE DATABASE IF NOT EXISTS TestReferenceDB;
USE DATABASE TestReferenceDB; 

// Create a test table. Data will be distributed over OrderID, CustomerID and partitioned by OrderDate.
DROP TABLE IF EXISTS dbo.Orders;
CREATE TABLE dbo.Orders
(
    OrderID int,
    CustomerID int,
    OrderDetailID int,
    OrderTotal double,
    OrderDate DateTime,
    INDEX clx_OrderID_CustomerID CLUSTERED(OrderID, CustomerID ASC)
)
PARTITIONED BY (OrderDate)
DISTRIBUTED BY HASH (OrderID, CustomerID) 
INTO 10;
```

**A.    ADD PARTITION**   
This example adds two partitions to the partitioned table, `Orders`.  The values used to partition on columns of DateTime types have to have their DateTimeKind set to DateTimeKind.Utc.
```
// Declare partition values and set DateTimeKind to DateTimeKind.Utc.
DECLARE @partition1 DateTime = new DateTime(2016, 01, 01, 00,00,00,00, DateTimeKind.Utc);
DECLARE @partition2 DateTime = @partition1.AddDays(1);

// Add two partitions in a single statement
ALTER TABLE TestReferenceDB.dbo.Orders
ADD PARTITION(@partition1), PARTITION(@partition2);

// This will not error since IF NOT EXISTS is used. (Alternative)
ALTER TABLE TestReferenceDB.dbo.Orders
ADD IF NOT EXISTS PARTITION (@partition2);
```

**B.    DROP PARTITION**   
This example drops a partition from the partitioned table, `Orders`.
```
DECLARE @partition1 DateTime = new DateTime(2016, 01, 01, 00,00,00,00, DateTimeKind.Utc);
ALTER TABLE TestReferenceDB.dbo.Orders
DROP PARTITION(@partition1);

// This will not error since IF EXISTS is used. (Alternative)
ALTER TABLE TestReferenceDB.dbo.Orders
DROP IF EXISTS PARTITION(@partition1);
```
  
### See Also  
* [PARTITION (U-SQL)](partition-u-sql.md)  
* [CREATE TABLE (U-SQL): Overview](create-table-u-sql-overview.md)  
* [TRUNCATE TABLE (U-SQL)](truncate-table-u-sql.md)
* [DROP TABLE (U-SQL)](drop-table-u-sql.md) 
* [CREATE TABLE (U-SQL): Creating a Table with Schema](create-table-u-sql-creating-a-table-with-schema.md)  
* [INSERT (U-SQL)](insert-u-sql.md) 
