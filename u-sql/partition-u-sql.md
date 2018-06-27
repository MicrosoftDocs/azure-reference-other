---
title: "PARTITION (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 889550b3-c98b-4df7-9870-9a742e7f190e
caps.latest.revision: 3
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# PARTITION (U-SQL)
The `PARTITION` intrinsic object returns `true` if the specified partition for the given table exists and the user has access to said table. Otherwise, `false` is returned.  The function will be evaluated at compile-time (and is thus constant-foldable).

## Syntax
<pre>
<a href="other-simple-built-in-types-and-literals.md">bool</a> PARTITION.EXISTS(
    <a href="#ident">Identifier</a>, 
    <a href="#partition_value">partition_value {, partition_value}</a>
).
</pre>


## Semantics of Syntax Elements  
- <a name="ident"></a>**`Identifier`**   
Identifies the table to be checked. If the Identifier is a three-part identifier, the table from the specified database and schema will be chosen. If the Identifier is a two-part identifier, then the table of the given schema and of the given name of the current static database context is chosen. If the identifier is a simple identifier, then the table of the given name in the current static database and schema context is chosen.  
    
  If the provided table does not exists or the user does not have access to it, the error `E_CSC_USER_DDLENTITYDOESNOTEXIST` is raised. 
      
- <a name="partition_value"></a>**`partition_value`**   
The typed values that define the particular partition of the table. The partition_value expression must be constant-foldable; otherwise, the error `E_CSC_USER_EXPRESSIONNOTCONSTANTFOLDABLE` is raised.
   
## Return Type
[bool](other-simple-built-in-types-and-literals.md)

## Examples    
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**Single column partition**    
```sql
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
    PARTITIONED BY (OrderDate)
    DISTRIBUTED BY HASH (OrderID, CustomerID)
);

DECLARE @partition1 DateTime = new DateTime(2016, 01, 01, 00,00,00,00, DateTimeKind.Utc);
DECLARE @partition2 DateTime = @partition1.AddDays(1);

IF (!PARTITION.EXISTS(TestReferenceDB.dbo.Orders, @partition1))
THEN
    ALTER TABLE TestReferenceDB.dbo.Orders ADD PARTITION (@partition1);
END;
```
<br />

**Multiple columns partition**   
```sql
USE DATABASE TestReferenceDB; 

DROP TABLE IF EXISTS dbo.PartTable;
CREATE TABLE dbo.PartTable
(
    PartId int,
    market string,
    description string,
    price decimal,
    INDEX idx CLUSTERED(price)
    PARTITIONED BY (PartId, market)
    DISTRIBUTED BY RANGE(price)
);

IF (!PARTITION.EXISTS(dbo.PartTable, 1, "en-us"))
THEN
    ALTER TABLE dbo.PartTable ADD PARTITION (1, "en-us");
END;

INSERT INTO PartTable(description, price)
            PARTITION(1,"en-us")
VALUES
   ("description 1", (decimal) 12.99),
   ("description 2", (decimal) 49.99);
```
<br />

## See Also
* [INSERT (U-SQL)](insert-u-sql.md)
* [ALTER TABLE (U-SQL): Adding and Removing Vertical Partition Buckets](alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md)
* [CREATE TABLE (U-SQL): Creating a Table with Schema](create-table-u-sql-creating-a-table-with-schema.md)
