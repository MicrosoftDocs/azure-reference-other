---
title: "INSERT (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-28"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: f272f4fb-6ba0-451d-b3c6-12f564c971bb
caps.latest.revision: 12
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# INSERT (U-SQL)
U-SQL provides the ability to insert rows an existing U-SQL table using the INSERT statement.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Insert_Statement :=                                                                                      
     'INSERT' ['INTO'] <a href="#Ident">Identifier</a> ['(' <a href="#Ident_l">Identifier_List</a> ')']  
     [<a href="#part_l">Partition_Label</a> | <a href="#int_cla">Integrity_Clause</a>]  
     <a href="#ins_src">Insert_Source</a>.
</pre></td></tr></table>
  
### Semantics of Syntax Elements    
-   <a name="Ident"></a>**`Identifier`**  
    The identifier specifies the [managed table](../USQL/u-sql-tables.md#man_ext_tabls) into which the data gets inserted. If the `Identifier` is a three-part identifier, the data will be inserted into the table in the specified database and schema. If it is a two-part identifier, then the data will be inserted into the table in the specified schema of the current database context. If the identifier is a simple identifier, then the data will be inserted into the table in the current database and schema context.  
    
    If the table of the given name does not exist, is an external table, or the user has no permissions to insert data into the table, an error is raised.  
  
    If the target table is a [vertically partitioned table](../USQL/create-table-u-sql-creating-a-table-with-schema.md), then either the `Insert_Partition_Label` or <a href="#int_cla">`Integrity_Clause`</a> has to be specified. The data will be automatically added to the specified/appropriate partitions, but no new partitions are being created. Partitions have to be explicitly created with [ALTER TABLE ADD PARTITION](../USQL/alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md).  
      
-   <a name="Ident_l"></a>**`Identifier_List`**    
    The optional list of identifier provides the list of columns in the target table into which data is being inserted. An error is raised if the list contains a column that does not exists in the target table.  
  
    If the list is not specified, the insertion source needs to provide values for all columns, if it is specified, the source needs to provide only values for the specified columns.  
  
    The values of the source are matched to the columns in order as they are specified in the identifier list. If the data types are not compatible, an error is raised.  
  
    A null value is inserted into a column that is not specified in the list. If that column has a not-nullable type (e.g., `int` instead of `int`?), an error is raised.  
  
- <a name="part_l"></a>**`Partition_Label`**   
  The optional partition label allows to specify an explicit partition into which the data will be inserted with the following syntax:
  <table><th>Syntax</th><tr><td><pre>
  Partition_Label :=                                                                                  
       'PARTITION' Static_Expression_Row_Constructor.<br />
  Static_Expression_Row_Constructor :=  
       '(' Static_Expression_List ')'.<br />
  Static_Expression_List :=  
       Static_Expression {',' Static_Expression}.<br />                        
  Static_Expression :=  
       <a href="textual-types-and-literals.md">string_literal</a> | <a href="numeric-types-and-literals.md">number_literal</a> | <a href="textual-types-and-literals.md">char_literal</a>
       | Static_Variable | binary_literal.</pre></td></tr></table>

  The label specifies the values for the partition column into which the data will be inserted. If this label is specified, then the partition columns cannot be specified in the target table’s identifier list. Instead, the values provided in the label will be inserted into the partition columns directly.   
  
  > [!NOTE]
  > If the partition column is of type DateTime, then the value that is provided in the partition label has to be using `DateTimeKind.UTC`.
  
  If the target table is not a partitioned table and the `Partition_Label` is specified an error will be raised.  
  
- <a name="int_cla"></a>**`Integrity_Clause`**    
  The optional integrity clause specifies what happens with data that does not fit into any of the available partitions with the following syntax: 
  <table><th>Syntax</th><tr><td><pre>
  Integrity_Clause :=                                                                                 
       'ON' 'INTEGRITY' 'VIOLATION' Integrity_Violation_Action.<br />
  Integrity_Violation_Action :=  
       '<a href="#ignr">IGNORE</a>'  
  |    <a href="#m_t_p">'MOVE' 'TO' Partition_Label</a>.
  </pre></td></tr></table>
  
  It provides the following options:    
  - <a name="ignr"></a>**`IGNORE`**    
    If the source contains a row for which no partition can be found, the row is ignored and not inserted.  
  
  - <a name="m_t_p"></a>**`MOVE TO Partition_Label`**      
    If the source contains a row for which no partition can be found, the row’s values (except for the partition column values) is moved into the specified partition and the partition column values are set to the specified partition label.  
  
    If the target table is not a partitioned table and the `Integrity_Clause` is specified an error will be raised.  
  
- <a name="ins_src"></a>**`Insert_Source`**    
  INSERT currently takes input from two sources: a [SELECT](../USQL/select-expression-u-sql.md) expression and the [VALUES](../USQL/values-expression-u-sql.md) row constructor:
  <table><th>Syntax</th><tr><td><pre>
  Insert_Source :=                                                                                    
       <a href="select-expression-u-sql.md">Select_Expression</a> 
  |    <a href="u-sql-select-selecting-from-the-values-table-value-constructor.md">Table_Value_Constructor_Expression</a>.
  </pre></td></tr></table>
    
  Note that the expressions need to provide values that fit into the target schema and are type compatible. Otherwise an error is raised. For more information about each of the expression please follow the links.  
  
> [!TIP]
> While INSERT allows incremental insertion into a table or table partition, it does currently does it by adding so called delta files (an artefact of the way the physical partition files for tables are “sealed” and cannot be append to incrementally). Thus doing a lot of incremental inserts can degrade query performance and it is recommended to only insert large batches of data instead of doing many small insertions.
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the table defined below.  
```
CREATE DATABASE IF NOT EXISTS TestReferenceDB;
USE DATABASE TestReferenceDB; 

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

**Partitioned Table - Basic Insert**   
This example adds two partitions to `Orders` if they do not already exist.  Then data is added into each partition.
```
// Add partitions if not exists
DECLARE @partition1 DateTime = new DateTime(2016, 01, 01, 00,00,00,00, DateTimeKind.Utc);
DECLARE @partition2 DateTime = @partition1.AddDays(1);
ALTER TABLE TestReferenceDB.dbo.Orders
ADD IF NOT EXISTS PARTITION(@partition1), PARTITION(@partition2);

// Alternate method to check for existing partition
IF (!PARTITION.EXISTS(TestReferenceDB.dbo.Orders, @partition1))
THEN
    ALTER TABLE TestReferenceDB.dbo.Orders ADD PARTITION (@partition1);
END;

// Insert a few records
INSERT INTO TestReferenceDB.dbo.Orders
(OrderID, CustomerID, OrderDetailID, OrderTotal)
PARTITION(@partition1)
VALUES
(1, 1, 1, 23098.90),
(2, 1, 2, 2456.99);

INSERT INTO TestReferenceDB.dbo.Orders
(OrderID, CustomerID, OrderDetailID, OrderTotal)
PARTITION(@partition2)
VALUES
(3, 1, 3, 535.00),
(4, 2, 1, 35000.76);
```

**Partitioned Table - INTEGRITY VIOLATION IGNORE**   
This example attempts to insert a record that does not fit into any of the available partitions.  With IGNORE, the record is ignored and not inserted.
```
INSERT INTO TestReferenceDB.dbo.Orders
(OrderID, CustomerID, OrderDetailID, OrderTotal, OrderDate)
ON INTEGRITY VIOLATION IGNORE
VALUES
(5, 4, 1, 3987.00, new DateTime(2016, 01, 02)),
(6, 3, 1, 24000.00, new DateTime(2016, 01, 03)); // no existing partition
```

**Partitioned Table - INTEGRITY VIOLATION MOVE**     
This example attempts to insert a record that does not fit into any of the available partitions.  With MOVE, the record is moved into a designated partition.  Here, the designated partition is for the year 2100.  This partition can be considered as the dumping partition for all records that do not fit into any of the available partitions.
```
// Create "dumping" partition
DECLARE @badPartition DateTime = new DateTime(2100, 01, 01, 00,00,00,00, DateTimeKind.Utc);
ALTER TABLE TestReferenceDB.dbo.Orders
ADD PARTITION(@badPartition);

// Insert a few records
INSERT INTO TestReferenceDB.dbo.Orders
(OrderID, CustomerID, OrderDetailID, OrderTotal, OrderDate)
ON INTEGRITY VIOLATION MOVE TO PARTITION (@badPartition)
VALUES
(7, 3, 2, 2000.00, new DateTime(2016, 01, 02)),
(8, 7, 1, 54279.00, new DateTime(2016, 01, 03)); // no existing partition
```
  
### See Also
* [PARTITION (U-SQL)](../USQL/partition-u-sql.md)   
* [ALTER TABLE (U-SQL): Adding and Removing Vertical Partition Buckets](../USQL/alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md)
* [OUTPUT Statement (U-SQL)](../USQL/output-statement-u-sql.md)  
* [CREATE TABLE (U-SQL): Creating a Table with Schema](../USQL/create-table-u-sql-creating-a-table-with-schema.md)
* [CREATE TABLE (U-SQL): Creating a Table from a Query](../USQL/create-table-u-sql-creating-a-table-from-a-query.md)  
