---
title: "U-SQL Tables | Microsoft Docs"
ms.custom: ""
ms.date: "04/26/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8a7b3cc8-df8b-4c6a-b981-7d8c657ef47e
caps.latest.revision: 30
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# U-SQL Tables
Similar to other database systems and SQL-inspired Big Data processing systems such as Hive, U-SQL uses the concept of a table to provide a data container that contains schematized structured data. Tables provide additional optimizations beyond a schematized view over unstructured files. Some of these optimizations consists of having the data arranged according to a key, the option to partition the table into several individually addressable partition buckets, the ability to internally partition the table or one of its partition buckets according to a partition key, and finally store the data in their native type serialization formats.   

U-SQL tables are backed by files. Each table partition is mapped to its own file, and each [INSERT](insert-u-sql.md) statement adds an additional file (unless a table is rebuilt with [ALTER TABLE REBUILD](alter-table-u-sql.md)).  If the file count of a table (or set of tables) grows beyond a certain limit and the query predicate cannot eliminate files (e.g., due to too many insertions), there is a large likely-hood that the compilation times out after 25 minutes.  Currently, if the number of table-backing files exceeds the limit of 3,000 files per job you will receive the following warning:

```   
Warning: WrnExceededMaxTableFileReadThreshold  
Message: Script exceeds the maximum number of table or partition files allowed to be read. This message will be upgraded to an error message in next deployment.
```
> [!NOTE]
> This limit only applies to reading from table-backing files. Normal files don't have an explicit limit and have a much higher limit in practice since they use a different execution plan. The limit also only applies to files that are actually read and ignores the files in table partitions which are not used by the query.
  
U-SQL tables can provide access to external data living in Azure SQL databases, Azure SQL Data Warehouses, and SQL Server instances in Azure VMs via external tables.  
  
The table concept also provides the ability to U-SQL to offer new storage formats, additional indexing schemes and access to other external data sets in the future without forcing the user to change their existing queries.  
  
### Managed versus External Tables <a name="man_ext_tabls"></a>   
U-SQL conceptually separates between *managed tables* and *external tables*.  
  
Managed tables “own” their data and both the table definition (the metadata) as well as the table data are being managed via the metadata system. Managed tables provide consistency between their schema and data and if a managed table gets deleted, the data it contains will be deleted as well.  
  
Furthermore, managed tables in U-SQL require an [index](u-sql-indexes.md) to be defined on them and provide [statistics](u-sql-statistics.md) on the data inside the table.  
  
External tables are tables that provide a table schema in the metadata system but only reference data that lives externally from the metadata system’s control. Thus there is no guarantee that the table schema is consistent with the data after the table has been created. The external data may be changed without going through the external table. And if an external table is being altered or dropped, the underlying data is not being affected or deleted.  
  
Currently U-SQL offers external tables over data stored in Azure SQL Databases, Azure SQL Data Warehouse, and SQL Server instances running in an Azure Virtual Machine. In order to create external tables over file data (as for example in Hive), one has to use U-SQL [Views](u-sql-views.md) or U-SQL [Table-Valued Functions](u-sql-functions.md) over the [EXTRACT](extract-expression-u-sql.md) expression.  
  
### Table DDL Statements    
Besides creating and dropping tables, U-SQL also provides the ability to add or drop partition buckets and to truncate the table content on managed tables without affecting the table schema:  

<table><th align="left">Syntax</th><tr><td><pre>
Table_DDL_Statement :=                                                                                   
     <a href="create-table-u-sql-overview.md">Create_Table_Statement</a>  
|    <a href="alter-table-u-sql.md">Alter_Table</a>    
|    <a href="alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md">Alter_Table_AddDrop_Partition_Statement</a>  
|    <a href="truncate-table-u-sql.md">Truncate_Table_Statement</a>
|    <a href="drop-table-u-sql.md">Drop_Table_Statement</a>.
</pre></td></tr></table>
  
### See Also  
* [CREATE TABLE (U-SQL): Overview](create-table-u-sql-overview.md)
* [ALTER TABLE (U-SQL)](alter-table-u-sql.md)
* [ALTER TABLE (U-SQL): Adding and Removing Vertical Partition Buckets](alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md)
* [TRUNCATE TABLE (U-SQL)](truncate-table-u-sql.md)
* [DROP TABLE (U-SQL)](drop-table-u-sql.md)

