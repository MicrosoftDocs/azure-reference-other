---
title: "CREATE TABLE (U-SQL): Creating Managed Tables | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 44965a00-d971-4ebc-ac7c-b667261d2f71
caps.latest.revision: 13
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# CREATE TABLE (U-SQL): Creating Managed Tables
U-SQL allows a table to be created by specifying a schema, or by specifying a query where the query’s result type implies the table’s schema. In both cases the table will have to have a clustered index specified in order to be able to contain data and both cases allow the table to be partitioned.  
  
> [!NOTE]
> All managed U-SQL tables are currently clustered tables where the cluster information is specified with a clustered index. In particular, other types of tables such as heaps and column store tables are not supported.

<table><th align="left">Syntax</th><tr><td><pre>
Create_Managed_Table_Statement :=                                                                        
    'CREATE' 'TABLE' [<a href="#INE">'IF' 'NOT' 'EXISTS'</a>] <a href="#ident">Identifier</a>   
    (<a href="#tbl_w_sch">Table_With_Schema</a> | <a href="#tbl_as_qry">Table_As_Query</a>).
</pre></td></tr></table>
   
### Semantics of Syntax Elements    
-   <a name="ident"></a>**`Identifier`**   
    Specifies the name of the schema. If the `Identifier` is a three-part identifier, the table will be created in the specified database and schema. If it is a two-part identifier, then the table will be created in the specified schema of the current database context. If the identifier is a simple identifier, then the table will be created in the current database and schema context.  
      
    If a table or other object of the given name already exists in the specified database and schema context or the user has no permissions to create a table, an error is raised.  
  
-   <a name="INE"></a>**`IF NOT EXISTS`**   
    If the optional `IF NOT EXISTS` is specified, then the statement creates the table if it does not already exist, or succeeds without changes if the table already exists and the user has permission to at least enumerate all existing tables.  
  
-   <a name="tbl_w_sch"></a>**`Table_With_Schema`**  
    A table can be specified by means of declaring a schema. See [CREATE TABLE (U-SQL): Creating a Table with Schema](create-table-u-sql-creating-a-table-with-schema.md) for more details.  
  
-   <a name="tbl_as_qry"></a>**`Table_As_Query`**   
    A table can be specified by means of declaring a schema. See [CREATE TABLE (U-SQL): Creating a Table from a Query](create-table-u-sql-creating-a-table-from-a-query.md) for more details.   
  
### See Also    
* [CREATE EXTERNAL TABLE (U-SQL)](create-external-table-u-sql.md)
* [CREATE TABLE (U-SQL): Creating a Table with Schema](create-table-u-sql-creating-a-table-with-schema.md)
* [CREATE TABLE (U-SQL): Creating a Table from a Query](create-table-u-sql-creating-a-table-from-a-query.md)




