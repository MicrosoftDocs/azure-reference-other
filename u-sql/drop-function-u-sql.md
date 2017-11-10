---
title: "DROP FUNCTION (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6e2c2be2-7ea8-42da-a392-acbaf92703df
caps.latest.revision: 7
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# DROP FUNCTION (U-SQL)
The `DROP TABLE` statement drops the specified function.  
  
> [!WARNING]
> **This operation cannot be undone!**

<table><th>Syntax</th><tr><td><pre>
Drop_Function_Statement :=                                                                               
       'DROP' 'FUNCTION' [<a href="#IE">'IF' 'EXISTS'</a>] <a href="#Ident">Identifier</a>.  
</pre></td></tr></table>
 
### Semantics of Syntax Elements    
-   <a name="Ident"></a>**`Identifier`**  
    Specifies the name of the table-valued function. If the `Identifier` is a three-part identifier, the function will be dropped in the specified database and schema. If it is a two-part identifier, then the function will be dropped in the specified schema of the current database context. If the identifier is a simple identifier, then the function will be dropped in the current database and schema context.  
  
    If a function of the given name does not exist, or the user has no permissions to drop the function, an error is raised.  
  
-   <a name="IE"></a>**`IF EXISTS`**    
    If the optional `IF EXISTS` is specified, then the statement drops the function if it already exists, or succeeds without changes if the function does not exist or the user has no permission to at least enumerate all existing functions.  
  
### Example    
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

The following statement drops the TVF with the name `SearchLogPerRegion` in the `TestReferenceDB’s` dbo schema if it exists and the user has permission to drop it:  
  
```
DROP FUNCTION IF EXISTS TestReferenceDB.dbo.SearchLogPerRegion;
```
  
### See Also    
* [U-SQL Functions](../USQL/u-sql-functions.md)  
* [U-SQL Table-valued Functions](../USQL/u-sql-table-valued-functions.md)  
* [CREATE FUNCTION (U-SQL): Table-valued Function](../USQL/create-function-u-sql-table-valued-function.md)  
* [Table-Valued Function Expression (U-SQL)](../USQL/table-valued-function-expression-u-sql.md) 
* [Data Definition Language (DDL) Statements (U-SQL)](../USQL/data-definition-language-ddl-statements-u-sql.md)   

