---
title: "DROP ASSEMBLY (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-13"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6d34f724-a0e0-4737-99ac-1d1623197863
caps.latest.revision: 8
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# DROP ASSEMBLY (U-SQL)
The `DROP ASSEMBLY` statement drops an assembly and any of its associated resources and files.  
  
Note that dropping an assembly is not checking for dependencies of other assemblies on the assembly to be dropped.  
  
> [!WARNING]
> **This operation cannot be undone!**
 
<table><th align="left">Syntax</th><tr><td><pre>
Drop_Assembly_Statement :=                                                                               
    'DROP' 'ASSEMBLY' [<a href="#IE">'IF' 'EXISTS'</a>] <a href="#ass_name">Assembly_Name</a>.<br />
<a href="#ass_name">Assembly_Name</a> := 
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements    
-   <a name="ass_name"></a>**`Assembly_Name`**  
    Specifies the [quoted or unquoted identifier](../u-sql/u-sql-identifiers.md) of the assembly to be dropped from the current static database context.  
  
-   <a name="IE"></a>**`IF EXISTS`**    
    If an assembly of the given name does not exist, or the user has no permissions to drop the assembly, an error is raised. If the optional `IF EXISTS` is specified, then the statement drops the assembly if it already exists, or succeeds without changes if the assembly does not exist or the user has no permission to at least enumerate all existing assemblies.  
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

```
USE DATABASE SQLSpatial;
DROP ASSEMBLY IF EXISTS SqlSpatial;
```
  
### See Also
* [U-SQL Assemblies](../u-sql/u-sql-assemblies.md)
* [CREATE ASSEMBLY (U-SQL)](../u-sql/create-assembly-u-sql.md)  
* [REFERENCE ASSEMBLY (U-SQL)](../u-sql/reference-assembly-u-sql.md)  
* [REFERENCE SYSTEM ASSEMBLY (U-SQL)](../u-sql/reference-system-assembly-u-sql.md)  
* [Extending U-SQL Expressions with User-Code](../u-sql/extending-u-sql-expressions-with-user-code.md)  
* [How to register U-SQL Assemblies in your U-SQL Catalog](https://blogs.msdn.microsoft.com/azuredatalake/2016/08/26/how-to-register-u-sql-assemblies-in-your-u-sql-catalog/)

