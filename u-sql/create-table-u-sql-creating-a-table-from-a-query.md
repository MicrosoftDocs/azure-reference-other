---
title: "CREATE TABLE (U-SQL): Creating a Table from a Query | Microsoft Docs"
ms.custom: ""
ms.date: "09/05/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6608d5d1-0b2b-47c0-9b86-7b6d7744121b
caps.latest.revision: 30
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# CREATE TABLE (U-SQL): Creating a Table from a Query
Often a script converts unstructured data in a file into a table, by first extracting the data using an [`EXTRACT`](extract-expression-u-sql.md) expression and then inserting it into a table after some optional transformations. In order to simplify the process, U-SQL provides the ability to create a table from a U-SQL query expression. The `CREATE TABLE AS` statement will infer the schema from the query expression and will create a clustered table, thus the clustered index needs to be provided as part of the `CREATE TABLE AS` statement.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Create_Managed_Table_As_Query_Statement :=                                                               
    'CREATE' 'TABLE' ['IF' 'NOT' 'EXISTS'] <a href="#ident">Identifier</a>  
    Table_As_Query.<br />
Table_As_Query :=  
    ( '(' <a href="#table_index">Table_Index</a> <a href="#h_partition_spec">Horizontal_Partition_Specification</a> ')'  
    | '(' <a href="#table_index">Table_Index</a> ')' <a href="#h_partition_spec">Horizontal_Partition_Specification</a> )  
    'AS' <a href="#qry_exp">Query_Expression</a><br />
<a href="#h_partition_spec">Horizontal_Partition_Specification</a> :=   
    'PARTITIONED' 'BY' Partition_Type  
    ['INTO' positive_integer_literal].
</pre></td></tr></table>

  
### Semantics of Syntax Elements  
-  <a name="ident"></a>**`Identifier`**   
  Specifies the name of the schema. If the Identifier is a three-part identifier, the table will be created in the specified database and schema. If it is a two-part identifier, then the table will be created in the specified schema of the current database context. If the identifier is a simple identifier, then the table will be created in the current database and schema context.  
  
    If a table or other object of the given name already exists in the specified database and schema context or the user has no permissions to create a table, an error is raised.   
  
- <a name="table_index"></a>**`Table_Index`**  
  Specifies the clustered index for the table. For more details on defining a table index, see [CREATE TABLE (U-SQL): Creating a Table with Schema](create-table-u-sql-creating-a-table-with-schema.md).  
  
-  <a name="h_partition_spec"></a>**`Horizontal_Partition_Specification`**   
    Only horizontal partitioning is currently supported with the CREATE TABLE AS statement. For more detail on the partitioning schemes and options see [CREATE TABLE (U-SQL): Creating a Table with Schema](create-table-u-sql-creating-a-table-with-schema.md).  
      
-  <a name="qry_exp"></a>**`Query_Expression`**    
   Provides the query expression that defines the schema of the data and provides the initial data values. Any [U-SQL query expression](query-statements-and-expressions-u-sql.md) can be used to create a table, including [SELECT](select-expression-u-sql.md), [EXTRACT](extract-expression-u-sql.md), `PRODUCE`, invocation of a TVF etc..  
  
### Examples    
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The examples below use the sample data, `/Samples/Data/SearchLog.tsv`, provided with your Data Lake Analytics account. See [Prepare source data](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-get-started-portal#prepare-source-data) for additional information.

**Creating a table from a query - an extract**   
The following example creates a table called `searchLogTable` from `SearchLog.tsv`.
```sql
DROP TABLE IF EXISTS dbo.searchLogTable;
CREATE TABLE dbo.searchLogTable (
       INDEX clx_UserId CLUSTERED(UserId ASC) 
       DISTRIBUTED BY HASH (UserId)
) AS EXTRACT UserId          int,
            Start           DateTime,
            Region          string,
            Query           string,
            Duration        int?,
            Urls            string,
            ClickedUrls     string
    FROM "/Samples/Data/SearchLog.tsv"
    USING Extractors.Tsv();
```

**Creating a table from a query - a rowset variable**   
The following example creates a table called `searchLogTable` from `SearchLog.tsv`.
```sql
CREATE DATABASE IF NOT EXISTS TestReferenceDB; 
USE DATABASE TestReferenceDB;

// Extract data from file
@data = 
    EXTRACT UserId          int,
            Start           DateTime,
            Region          string,
            Query           string,
            Duration        int?,
            Urls            string,
            ClickedUrls     string
    FROM "/Samples/Data/SearchLog.tsv"
    USING Extractors.Tsv();

// Create table based on extraction and populate table
DROP TABLE IF EXISTS dbo.searchLogTable;
CREATE TABLE dbo.searchLogTable (
       INDEX clx_UserId CLUSTERED(UserId ASC) 
       DISTRIBUTED BY HASH (UserId)
) AS SELECT * FROM @data; 
```

**Creating a table from a query - another table**  
The following example creates a table called `searchLogTableCopy` from `searchLogTable`, created from prior example.
```
DROP TABLE IF EXISTS dbo.searchLogTableCopy;
CREATE TABLE dbo.searchLogTableCopy (
       INDEX clx_UserId CLUSTERED(UserId ASC) 
       DISTRIBUTED BY HASH (UserId)
) AS SELECT * FROM dbo.searchLogTable; // Can also use a View
```

**Creating a table from a query - invocation of a TVF**  
The following example creates a table called `searchLogFromFunction` by invoking the fuction `tvf_SearchLog` which was created from [Basic Syntax - tvf_SearchLog](create-function-u-sql-table-valued-function.md#tvf_SearchLog).
```sql
DROP TABLE IF EXISTS dbo.searchLogFromFunction;
CREATE TABLE dbo.searchLogFromFunction (
    INDEX clx_UserId CLUSTERED(UserId ASC)
    DISTRIBUTED BY HASH (UserId) 
    ) AS dbo.tvf_SearchLog();
```

  
### See Also  
* [CREATE TABLE (U-SQL): Overview](create-table-u-sql-overview.md)  
* [ALTER TABLE (U-SQL): Adding and Removing Vertical Partition Buckets](alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md)
* [TRUNCATE TABLE (U-SQL)](truncate-table-u-sql.md)
* [DROP TABLE (U-SQL)](drop-table-u-sql.md)   
