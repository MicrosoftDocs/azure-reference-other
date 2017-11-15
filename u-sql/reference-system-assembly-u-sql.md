---
title: "REFERENCE SYSTEM ASSEMBLY (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-13"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ae98386b-9a32-4341-97e0-057a96ce4289
caps.latest.revision: 10
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# REFERENCE SYSTEM ASSEMBLY (U-SQL)
U-SQL provides a small set of preloaded system assemblies for the C# core and the most commonly used C# functions. The set is being kept small to reduce the amount of assemblies that the query processor will have to load and process at runtime.  
  
In order to load additional system assemblies, U-SQL provides the REFERENCE SYSTEM ASSEMBLY statement that allows to load additional system assemblies for the script.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Reference_System_Assembly_Statement :=                                                                   
     'REFERENCE' 'SYSTEM' 'ASSEMBLY' Assembly_Name.<br />
<a href="#ass_name">Assembly_Name</a> := 
     <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre></td></tr></table>
 
### Semantics of Syntax Elements  
-   <a name="ass_name"></a>**`Assembly_Name`**  
    Specifies the C# name of the system assembly as a [quoted or unquoted identifier](u-sql-identifiers.md) of the assembly to be loaded. Note: This name is not resolved against the U-SQL meta data catalog.   
  
### Preloaded System Assemblies  
The following system assemblies and namespaces are preloaded and thus their public objects can be used directly in any U-SQL expression:   
-   Assemblies:  
    - mscorlib.dll  
    - System.dll  
    - System.Core.dll  
    - System.Data.dll  
-   Namespaces:  
    - System  
    - System.Data  
    - System.Text  
    - System.Text.RegularExpressions  
    - System.Linq  
  
In addition, the U-SQL’s own system assemblies and namespaces for its types and associated functions, constructors and methods are also preloaded.   
  
-   Assemblies:  
    - Microsoft.Analytics.Interfaces.dll  
    - Microsoft.Analytics.Types.dll  
-   Namespaces:  
    - Microsoft.Analytics.Types  
    - Microsoft.Analytics.Types.Sql  
    - Microsoft.Analytics.Interfaces  
  
Even though one can use short-form references to the preloaded objects, it is recommended to always fully qualify the objects to avoid conflicts with user objects.  
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

The following statement references the system assembly System.XML, so its objects can be used in the script:  
```
REFERENCE SYSTEM ASSEMBLY [System.XML];  
```
  
### See Also
* [U-SQL Assemblies](u-sql-assemblies.md)
* [CREATE ASSEMBLY (U-SQL)](create-assembly-u-sql.md)  
* [REFERENCE ASSEMBLY (U-SQL)](reference-assembly-u-sql.md)  
* [DROP ASSEMBLY (U-SQL)](drop-assembly-u-sql.md)  
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)  
  
  
