---
title: "CREATE TABLE (U-SQL): Creating a Table with Schema | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-28"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b24dc8d2-059b-480d-9280-6cde61e239cf
caps.latest.revision: 31
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CREATE TABLE (U-SQL): Creating a Table with Schema
U-SQL allows a managed table to be created by specifying a schema. The table will have to have a clustered index specified in order to be able to contain data and the table will be partitioned.  
  
> [!NOTE]
> All [managed](u-sql-tables.md#man_ext_tabls) U-SQL tables are currently clustered tables where the cluster information is specified with a clustered index. In particular, other types of tables such as heaps and column store tables are not supported.
  
When creating a managed U-SQL table with a schema, a table schema has to be provided that contains at least one table column definition.  

<table><th>Syntax</th><tr><td><pre>
Create_Managed_Table_With_Schema_Statement :=                                                            
     'CREATE' 'TABLE' [<a href="#INE">'IF' 'NOT' 'EXISTS'</a>] <a href="#ident">Identifier</a><br />  
<a href="#tbl_sch">     Table_With_Schema</a>.
<br />
<a href="#tbl_sch">Table_With_Schema</a> :=  
     '(' { <a href="#col_def">Column_Definition</a> ',' }   
         [ <a href="#table_index">Table_Index</a> <a href="#partition_spec">Partition_Specification</a> ]     
         { ',' <a href="#col_def">Column_Definition</a> } ')'  
|    '(' { <a href="#col_def">Column_Definition</a> ',' }   
         [ <a href="#table_index">Table_Index</a> ]
         { ',' <a href="#col_def">Column_Definition</a> } ')' <a href="#partition_spec">Partition_Specification</a>.  
</pre></td></tr></table>
 
### Semantics of Syntax Elements    
-   <a name="ident"></a>**`Identifier`**   
    Specifies the name of the schema. If the `Identifier` is a three-part identifier, the table will be created in the specified database and schema. If it is a two-part identifier, then the table will be created in the specified schema of the current database context. If the identifier is a simple identifier, then the table will be created in the current database and schema context.  
    
    If a table or other object of the given name already exists in the specified database and schema context or the user has no permissions to create a table, an error is raised.  
  
-   <a name="INE"></a>**`IF NOT EXISTS`**   
    If the optional `IF NOT EXISTS` is specified, then the statement creates the table if it does not already exist, or succeeds without changes if the table already exists and the user has permission to at least enumerate all existing tables.  
  
-   <a name="tbl_sch"></a>**`Table_With_Schema`**   
    A table schema contains at least one column definition (note the above syntax is slightly simplified for readability) and can optionally contain a table index and a partition specification. The table index is optional in the definition of the table and the partition specification can either follow the index specification or can follow the table schema. If the partition specification follows the schema, then the schema needs to contain the index specification.  
    > [!NOTE]
    > While the index definition is optional as part of the table definition, no data can be inserted into the table until an index has been defined. If the index definition is not part of the table definition, then a [CREATE CLUSTERED INDEX](u-sql-indexes.md) statement has to be executed before data can be inserted into the table.
  
- <a name="col_def"></a>**`Column_Definition`**  
A column definition is of the form
  <table><th>Syntax</th><tr><td><pre>
Column_Definition :=                                                                                
        <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> <a href="built-in-u-sql-types.md">Built_in_Type</a>.
</pre></td></table>
  
    Each column has an identifier that can be either a [quoted or unquoted identifier](u-sql-identifiers.md) which is typed with one of the [built-in U-SQL types](built-in-u-sql-types.md). Note that there are currently no constraints such as primary key, foreign key, unique etc. supported. Unlike in the case of traditional SQL tables, nullability is part of the type and not a column property.  
  
- <a name="table_index"></a>**`Table_Index`**  
  The table index defines the clustered index of the table. It specifies the name of the index that is local to the table as a [quoted or unquoted identifier](u-sql-identifiers.md) and by providing a list of columns that determine how and in which order the rows will be ordered. It basically determines how the data will be physically stored in the clustered table.  
  
  The table index syntax looks like  
  <table><th>Syntax</th><tr><td><pre>
Table_Index :=                                                                                      
        'INDEX' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>   
        'CLUSTERED' '(' Sort_Item_List ')'.<br />
Sort_Item_List :=  
        Sort_Item {',' Sort_Item}.<br />   
Sort_Item :=                                                                    
        <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> [Sort_Direction].<br />
Sort_Direction :=
        'ASC' | 'DESC'. 
</pre></td></table>  
  
- <a name="partition_spec"></a>**`Partition_Specification`**  
  The partition specification provides information how the data inside the table is being partitioned and distributed.  
  
  If the table index is being provided, the partition specification has to be provided as well. The syntax looks like:  
   
  <table><th>Syntax</th><tr><td><pre>
Partition_Specification :=                                                                          
        [ 'PARTITIONED' ['BY'] '(' Identifier_List ')' ]   
        Distribution_Specification.<br />
Identifier_List :=  
        <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> {',' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>}.<br />
Distribution_Specification :=  
        'DISTRIBUTED' ['BY'] Distribution_Scheme ['INTO' integer_or_long_literal].<br /><br />
<a href="#dis_sch">Distribution_Scheme</a> :=  
        '<a href="#rng">RANGE</a>' '(' Sort_Item_List ')'  
|       '<a href="#hsh">HASH</a>' '(' Identifier_List ')'   
|       '<a href="#dhsh">DIRECT' 'HASH</a>' '(' Identifier ')'   
|       '<a href="#rnd_rob">ROUND' 'ROBIN</a>'.
</pre></td></table>  

  For detailed semantics about partitioning see the section on <a href="#partitioning">partitioning</a>.  
  
### <a name="partitioning"></a> U-SQL Table Partitions and Distributions  
U-SQL Tables can be partitioned in two-levels: the higher-level coarse-grained _partitioning_ into addressable partitions and the lower-level fine grained _distribution_ within a table or a partition.   
  
### U-SQL Table Partition   
Many use cases around data life cycle management, such as loading of daily or hourly data, require that one can add individual partitions and manage them separately. This is best done with  _partitioning_ a table into individually addressable partitions. Each of these partitions have to then explicitly be added with [`ALTER TABLE ADD PARTITION`](alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md) and can be removed with [`ALTER TABLE DROP PARTITION`](alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md). In addition, the query processor will perform partition elimination on supported predicates.  
  
Currently U-SQL only allows partitioning in conjunction with <a href="#hsh">`HASH`</a> and <a href="#rnd_rob">`ROUND ROBIN`</a> distributions.  
  
Note that the types of the columns used to specify partitioning schemes have to be comparable. In particular that means that the type cannot be a complex type. Additionally, in order to provide precise and deterministic semantics for  partitioning on `DateTime` values, the values used to partition on columns of `DateTime` types have to have their `DateTimeKind` set to `DateTimeKind.Utc`.  
  
[//]: # "COMMENT: For best practices and guidance on which columns to choose as index key, how to select the most appropriate partitioning schemes, bucket size, and partition keys please refer to ADDLINK."  
  
### <a name="dis_sch"></a>U-SQL Table Distributions   
Every table has to provide at least a _distribution_ scheme that will partition the data inside the table (or inside each  partition) according to the specified scheme.   
  
Currently U-SQL supports four distribution schemes:   
-    <a name="rng"></a>**`RANGE`**    
    Based on a set of ordered columns. Tables distributed by RANGE needs to provide a list of columns that will determine the ranges over which to distribute. The system will determine the bounds for the distributions.  Each distribution contains all the rows between those bounds, according to the sort order given and an artificial MAX and MIN value to close the first and last distributions.  For any distribution P that has a left boundary value L and a right boundary value R, P will contain the range from L inclusive to R-1. The value R will be in the next distribution. If the data is ordered in ascending order, then L corresponds to the lower bound and R to the upper bound, if the data is ordered in descending order then L corresponds to the high value and R to the low value. The column order is significant in determining the distribution and ASC/DESC optionally specifies the order and is defaulted to ascending.   
    
-    <a name="hsh"></a>**`HASH`**    
    Based on a set of columns. Tables distributed by HASH requires a list of columns that will be used to route each row individually to a distributions based on a hash of the columns specified.  
    
-    <a name="dhsh"></a>**`DIRECT HASH`**   
    Based on single column of an integral type. The DIRECT HASH distribution scheme provides direct control of mapping a row into the distribution by using the value in the integer column as the distribution bucket id.   
    
-    <a name="rnd_rob"></a>**`ROUND ROBIN`**   
    ROUND ROBIN assigns rows to distributions individually in round robin fashion without reference to the values they contain.  Each distribution should have approximately the same number of rows.  
  
Note that each of the distribution schemes has certain advantages based on the characteristics of the data and the type of queries most frequently run against it. In particular, they should be chosen for distribution sizing, filter predicate selectivity and join comparisons to reduce data reshuffling in case of distribution misalignments.   
  
For example, a range distribution is more likely helping if the query is looking for data in a single distribution using either a range or point query, and a hash distribution is beneficial if point queries are used, but they can introduce data skew if the data is unevenly distributed. Such data skew can hurt query performance if the query needs to query across many distributions. In that case <a href="#rnd_rob">`ROUND ROBIN`</a> will eliminate most of the data skew and provide better performance.  
  
The <a name="INTO"></a>`INTO` clause specifies the number of buckets for the distribution schemes. The value has to be greater than or equal to 2 and less than or equal to 2500. If it is omitted, then U-SQL will give the query processor the flexibility to use as many distribution buckets as appropriate to avoid some costly reshuffling of data during the insertion. The query processor will choose the default number for hash distribution buckets depending on the size of the first data to be inserted into the table in the following way:    
 
U-SQL has a short list of candidate bucket numbers ({ 2, 10, 20, 60, 120, 240, 480 }). It chooses the default from this list based on the estimated data size for the first insert and the upper bound average distribution size limit of 2GB. It uses the smallest number from the list which will produce the average distribution size smaller or equal to the 2GB upper bound. 
  
If the `INTO` clause is specified, then the data will be distributed into the specified number.  
   
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**Basic Syntax**   
```
CREATE TABLE dbo.Employees
(
    EmpID int,
    EmpName string,
    DeptID int,
    Salary int?,
    StartDate DateTime,
    INDEX clx_EmpID CLUSTERED(EmpID ASC)
)
DISTRIBUTED BY HASH(EmpID);
```

**Basic Syntax - Alternative Method**   
```
CREATE TABLE dbo.Employees
(
    EmpID int,
    EmpName string,
    DeptID int,
    Salary int?,
    StartDate DateTime,
    INDEX clx_EmpID CLUSTERED(EmpID ASC) DISTRIBUTED BY HASH(EmpID)
);
```

**Partitioned Table**   
This examples creates a partitioned table. Data will be distributed over OrderID, CustomerID and partitioned by OrderDate.
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

  
### See Also  
* [PARTITION (U-SQL)](partition-u-sql.md)  
* [U-SQL Tables](u-sql-tables.md)  
* [CREATE TABLE (U-SQL): Overview](create-table-u-sql-overview.md)  
* [CREATE TABLE (U-SQL): Creating Managed Tables](create-table-u-sql-creating-managed-tables.md)   
* [CREATE TABLE (U-SQL): Creating a Table from a Query](create-table-u-sql-creating-a-table-from-a-query.md)  
* [CREATE EXTERNAL TABLE (U-SQL)](create-external-table-u-sql.md)  
* [ALTER TABLE (U-SQL): Adding and Removing Vertical Partition Buckets](alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md)  
* [TRUNCATE TABLE (U-SQL)](truncate-table-u-sql.md)  
* [DROP TABLE (U-SQL)](drop-table-u-sql.md) 
