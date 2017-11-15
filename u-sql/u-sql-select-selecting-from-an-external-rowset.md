---
title: "U-SQL SELECT Selecting from an External Rowset | Microsoft Docs"
ms.custom: ""
ms.date: "2017-04-11"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: fd604915-bbe9-4f21-adfb-6a84b1b08f5d
caps.latest.revision: 22
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL SELECT Selecting from an External Rowset
U-SQL allows selecting from an external data source in three ways:  
  
1.  By using the [external table’s](../USQL/u-sql-tables.md) identifier like any other table’s identifier.  
  
2.  By using the external rowset expression to identify a rowset such as a table or view in the specified data source.  
  
3.  By using the external rowset expression to send a query string to the external data source for remote execution. The query string is in the form of the query language that is supported by that data source. E.g., if the data source is an Azure SQL Database, then the query string would be T-SQL.  
  
In all cases, the query will be executed based on the chosen query remoting option [REMOTEABLE_TYPES](../USQL/create-data-source-u-sql.md#rmv_typ) in the data source definition. If the definition allows an expression on a specific type to be remoted, and U-SQL knows how to translate it into a remote query expression, then parts of the U-SQL SELECT statement will be sent to the external data source’s query engine for execution.  
  
<table><th align="left">Syntax</th><tr><td><pre>
External_Rowset_Expression :=                                                                            
     'EXTERNAL' <a href="#dsi">Datasource_Identifier</a> <a href="#l_csl">'LOCATION' csharp_string_literal</a>   
|    'EXTERNAL' <a href="#dsi">Datasource_Identifier</a> <a href="#E_csl">'EXECUTE' csharp_string_literal</a>.<br />
<a href="#dsi">Datasource_Identifier</a> := 
     <a href="u-sql-identifiers.md">DB_Object_Identifier</a>.
</pre></td></tr></table>

### Semantics of the Syntax Elements    
-   **`EXTERNAL`** <a name="dsi"></a>**`Datasource_Identifier`**  
    Specifies the external data source. If the identifier is a two-part identifier, then the data source of the specified database is being queried. If the identifier is a single identifier, then the data source in the current static database context will be queried. If a data source of the given name does not exist in the database context or the user has no permissions to query the data source, an error is raised.  
    
    An error is also raised if the connection to the remote data source could not be established.  
  
-   <a name="l_csl"></a>**`LOCATION csharp_string_literal`**  
    The string literal identifies a schema qualified name of a remote table or view to be queried. If a table or view of the specified name does not exist or the user does not have access to it, an error is raised.  
  
-   <a name="E_csl"></a>**`EXECUTE csharp_string_literal`**  
    The string literal contains a query expression in the language supported by the remote data source. E.g., if the data source is an Azure SQL Database, then the query string would be T-SQL. If the query is malformed, or accesses objects that do not exist or the user does not have access to it, an error is raised. The same holds if the query returns values of types that are not supported by U-SQL’s remote query capabilities.  
    
    Note that some properties, such as the remote system’s error language, can be set in the data source definition’s [PROVIDER_STRING](../USQL/create-data-source-u-sql.md#p_strng) option.

> [!NOTE]
>  A rowset alias has to be specified when using an external rowset expression in the SQL [FROM](../USQL/from-clause-u-sql.md) clause.

### Examples
Examples utilize the data source created in the examples from [CREATE DATA SOURCE (U-SQL)](../USQL/create-data-source-u-sql.md).

**Using LOCATION**   
```
USE DATABASE TestReferenceDB;
@results =
    SELECT DateTime.Now AS dayTime, *
    FROM EXTERNAL MyAzureSQLDBDataSource LOCATION "dbo.BuildVersion";

OUTPUT @results
TO "/Output/ReferenceGuide/DDL/DataSources/Query2A.csv"
USING Outputters.Csv(outputHeader: true);
```

**Using EXECUTE**   
```
USE DATABASE TestReferenceDB;
@results =
    SELECT *
    FROM EXTERNAL MyAzureSQLDBDataSource EXECUTE 
        @"SELECT @@SERVERNAME AS serverName, GETDATE() AS dayTime, DB_NAME() AS databaseName, * FROM dbo.BuildVersion WITH (NOLOCK)";

OUTPUT @results
TO "/Output/ReferenceGuide/DDL/DataSources/Query1A.csv"
USING Outputters.Csv(outputHeader: true);
```
  
### See Also 
* [Query Statements and Expressions (U-SQL)](../USQL/query-statements-and-expressions-u-sql.md)  
* [Data Modification Language (DML) Statements (U-SQL)](../USQL/data-modification-language-dml-statements-u-sql.md)    
* [Output Statement (U-SQL)](../USQL/output-statement-u-sql.md)  
* [U-SQL Data Sources](../USQL/u-sql-data-sources.md) 

