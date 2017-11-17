---
title: "U-SQL Packages | Microsoft Docs"
ms.custom: ""
ms.date: "2017-05-02"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 01ee7364-1a44-4892-9808-973c663e26f0
caps.latest.revision: 3
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Packages
A U-SQL package allows the bundling of commonly used constant declarations, assembly references and resource deployments in a single meta data object to make sharing and referencing easier.

U-SQL packages can be nested, and can encapsulate references to use or export to the caller/importer of the package.

Packages can be parameterized (e.g. for context or versioning).

The identifiers referenced inside a package definition will be resolved in the static context of the package definition, similarly to table-valued functions and procedures.

If conflicting assemblies or references are being referenced, imported or deployed, errors are raised once a package gets imported in the main U-SQL script.

Since packages are a meta data object they are subject to the database-level access control.

> [!NOTE]
> No DDL is allowed inside a package (e.g. CREATE/ALTER/DROP .. etc).
  
<table><th align="left">Syntax</th><tr><td><pre>
Package_DDL_Statement :=                                                                                 
     <a href="create-package-u-sql.md">Create_Package_Statement</a>
|    <a href="drop-package-u-sql.md">Drop_Package_Statement</a>.<br />
Import_Package_Statement :=
     <a href="import-package-u-sql.md">Import_Package_Statement</a>.
</pre></td></tr></table>

### See Also    
* [U-SQL Assemblies](u-sql-assemblies.md)  
* [U-SQL Programmability Guide](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide)  


 
