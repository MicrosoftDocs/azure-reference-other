---
title: "DROP PACKAGE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-05-02"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 1d09fb05-cef8-4fae-a203-fed39f02168b
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# DROP PACKAGE (U-SQL)
The `DROP PACKAGE` statement drops packages. As in the case with other meta data objects, a package gets dropped even if another [package](u-sql-packages.md), [table-valued function](u-sql-table-valued-functions.md) or [procedure](u-sql-procedures.md) depends on it.

<table><th>Syntax</th><tr><td><pre>
Drop_Package_Statement :=                                                                                
    'DROP' 'PACKAGE' [<a href="#IE">'IF' 'EXISTS'</a>] <a href="#Ident">Identifier</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements  
-   <a name="IE"></a>**`IF EXISTS`**   
    If a package of the given name does not exist, or the user has no permissions to drop the package, an error is raised. If the optional `IF EXISTS` is specified, then the statement drops the package if it already exists, or succeeds without changes if the package does not exist or the user has no permission to at least enumerate all existing packages. 
     
-   <a name="Ident"></a>**`Identifier`**   
    Specifies the name of the package to be dropped. If the package name is a fully-specified three-part name, the package in the specified database and schema will be dropped. If the name is a two-part name, the package will be dropped in the current database context and specified schema. If the name is a simple identifier, then the package will be dropped in the current database and schema context. 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples utilize the packages created from [CREATE PACKAGE (U-SQL)](create-package-u-sql.md).
```
// Will error if not exists
USE DATABASE TestReferenceDB;
DROP PACKAGE XMLFiles;

// Will not error if not exists
DROP PACKAGE IF EXISTS TestReferenceDB.dbo.XMLorJSON;
```
### See Also
* [CREATE PACKAGE (U-SQL)](create-package-u-sql.md)
* [IMPORT PACKAGE (U-SQL)](import-package-u-sql.md)