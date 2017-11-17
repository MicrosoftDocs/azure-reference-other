---
title: "CREATE EXTERNAL TABLE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: f3ce61c3-505d-42a6-b64d-fc364e513eff
caps.latest.revision: 21
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CREATE EXTERNAL TABLE (U-SQL)
U-SQL provides the ability to create external tables over data that is not owned by the U-SQL metadata object itself. Currently external tables are offered over data stored in Azure SQL Databases and are created with the CREATE EXTERNAL TABLE statement.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Create_External_Table_Statement :=                                                                       
    'CREATE' 'EXTERNAL' 'TABLE' [<a href="#INE">'IF' 'NOT' 'EXISTS'</a>] <a href="#ident">Identifier</a>   
    '(' <a href="#col_def">Column_Definition_List</a> ')' <a href="#table_external_spec">Table_External_Specification</a>.
</pre></td></tr></table>
  
### Semantics of Syntax Elements  
This statement creates a new external table with the specified name given by [Identifier](#ident) with the provided U-SQL table schema based on the external data provided by the [Table_External_Specification](#table_external_spec).   
  
- <a name="ident"></a>**`Identifier`**    
  If the Identifier is a three-part identifier, the table will be created in the specified database and schema. If it is a two-part identifier, then the table will be created in the specified schema of the current database context. If the identifier is a simple identifier, then the table will be created in the current database and schema context.   

  If a table of the given name already exists in the specified database and schema context or the user has no permissions to create a table, an error is raised.   
  
- <a name="INE"></a>**`IF NOT EXISTS`**    
If the optional `IF NOT EXISTS` is specified, then the statement creates the table if it does not already exist, or succeeds without changes if the table already exists and the user has permission to at least enumerate all existing tables.  
      
- <a name="col_def"></a>**`Column_Definition_List`**   
  Defines the table schema as follows:  
  <table><th>Syntax</th><tr><td><pre>
  Column_Definition_List :=                                                                           
      Column_Definition { ',' Column_Definition }.
  </pre></td></tr></table>
    
  - **`Column_Definition`**  
    A column definition is of the form  
    <table><th>Syntax</th><tr><td><pre>
    Column_Definition :=                                                                           
        <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> <a href="built-in-u-sql-types.md">Built_in_Type</a>.
    </pre></td></tr></table>
 
    Each column has an identifier that can be either a [quoted or unquoted identifier](u-sql-identifiers.md) which is typed with one of the [built-in U-SQL types](built-in-u-sql-types.md). Each column identifier has to match to one of the column identifiers in the external table and the external columns data type (e.g., the SQL type in the Azure SQL database) will be mapped to the specified U-SQL type. If the mapping is not supported, an error is raised.  

- <a name="table_external_spec"></a>**`Table_External_Specification`**  
  The external location where the data is managed is referenced with the following specification:

  <table><th>Syntax</th><tr><td><pre>
  Table_External_Specification :=                                                                     
      'FROM' Datasource_Identifier 'LOCATION' <a href="expressions-u-sql.md">Static_String_Expression</a>.<br /> 
  Datasource_Identifier :=                                                        
      <a href="u-sql-identifiers.md">DB_Object_Identifier</a>.
  </pre></td></tr></table>
 
  The data source identifier is the name of the data source that has been created with the [CREATE DATA SOURCE](create-data-source-u-sql.md) statement. The static string expression provided as the location determines the actual rowset resource in the external data source that is being mapped to the U-SQL external table.  
  
  If the data source is a SQL database, then the location is the schema-qualified name of a table or view in the SQL database. Its schema is mapped to the external table’s schema in the following way:   
  - Any name in the column definition is mapped to the same name in the external table. If the external table’s naming is case-sensitive then the names have to exactly match, if the naming is case-insensitive, then the names are matched case-insensitively.   
  - Any matched column has to have a U-SQL type in the column definition that is compatible with the external table’s column’s type, or an error is raised.  
  - If a column is specified in the column definition that does not exist in the external table an error is raised.  
  - If the external table has a column that is not specified in the column definition, then that column is not accessible via the external table.  
  
  An error is raised if the remote data source cannot be accessed, e.g., because the data source has disappeared, closed the firewall, or the credentials to access the remote data source have changed.  
  
### Example
This example continues with the Data Source created from the example at [CREATE DATA SOURCE (U-SQL)](create-data-source-u-sql.md).
```
// External Table - Create
USE DATABASE TestReferenceDB;
CREATE EXTERNAL TABLE IF NOT EXISTS dbo.BuildVersion_Local
(
    SystemInformationID byte,
    [Database Version] string,
    VersionDate DateTime,
    ModifiedDate DateTime
)
FROM MyAzureSQLDBDataSource LOCATION "[dbo].[BuildVersion]";


// External Table - Query
@result =
    SELECT *
    FROM TestReferenceDB.dbo.BuildVersion_Local;

OUTPUT @result
TO "/Output/ReferenceGuide/DDL/Tables/ExternalTableQuery1.csv"
USING Outputters.Csv();
```
  
### See Also
* [U-SQL Tables](u-sql-tables.md)  
* [CREATE TABLE (U-SQL): Creating Managed Tables](create-table-u-sql-creating-managed-tables.md) 
* [CREATE TABLE (U-SQL): Creating a Table with Schema](create-table-u-sql-creating-a-table-with-schema.md) 
* [CREATE TABLE (U-SQL): Creating a Table from a Query](create-table-u-sql-creating-a-table-from-a-query.md)  
* [ALTER TABLE (U-SQL): Adding and Removing Vertical Partition Buckets](alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md)  
* [TRUNCATE TABLE (U-SQL)](truncate-table-u-sql.md)  
* [DROP TABLE (U-SQL)](drop-table-u-sql.md)    
