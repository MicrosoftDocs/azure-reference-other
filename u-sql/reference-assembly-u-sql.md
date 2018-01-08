---
title: "REFERENCE ASSEMBLY (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "10/13/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6698dd77-510f-4a80-88a1-1bda4b9774ed
caps.latest.revision: 14
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# REFERENCE ASSEMBLY (U-SQL)
In order to use a [user-defined c# functions](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-functions---udf), [user-defined aggregator](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-aggregates--udagg) or [user-defined operator](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-objects--udo), the assemblies that contain their code need to be referenced in the U-SQL script.  
  
The system then loads these assemblies to resolve names and types during compile time and load the code for execution.  
  
Note that all assemblies that are needed at compile time, as well as all assemblies that are needed during execution will need to be referenced. Otherwise an error will be raised.   
  
These requirements however mean, that an assembly that is used by a function that is not directly nor indirectly being used in the script, may not need to be referenced, thus reducing the amount of data that a script has to load for execution.  

When referencing multiple assemblies that contain additional files, their names across the entire collection of referenced assemblies in the script need to be unique. In case file names conflict, the error `E_CSC_USER_CONFLICTINGASSEMBLYFILE` is raised. The file name paths of additional assembly files also cannot conflict with file name paths of deployed resources. In case they conflict, the error `E_CSC_USER_SAMERESOURCEWITHDIFFERENTPATH` is raised.
  
<table><th align="left">Syntax</th><tr><td><pre>
Reference_User_Assembly_Statement :=                                                                     
     'REFERENCE' 'ASSEMBLY' Global_Assembly_Identifier.<br />
<a href="#ass_name">Global_Assembly_Identifier</a> := 
     <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre></td></tr></table>
  
### Semantics of Syntax Elements
- <a name="ass_name"></a>**`Global_Assembly_Identifier`**  
Specifies the [quoted or unquoted identifier](u-sql-identifiers.md) of the assembly to be loaded. The assembly name is resolved against the current static database context.   
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

```
USE DATABASE SQLSpatial;

REFERENCE SYSTEM ASSEMBLY [System.Xml];
REFERENCE ASSEMBLY SqlSpatial;

USING Geometry = Microsoft.SqlServer.Types.SqlGeometry;
USING Geography = Microsoft.SqlServer.Types.SqlGeography;
USING SqlChars = System.Data.SqlTypes.SqlChars;

@spatial =
    SELECT * FROM (VALUES 
                   // The following expression is not using the native DDL
                   ( Geometry.Point(1.0,1.0,0).ToString()),    
                   // The following expression is using the native DDL
                   ( Geometry.STGeomFromText(new SqlChars("LINESTRING (100 100, 20 180, 180 180)"), 0).ToString()) 
                  ) AS T(geom);

OUTPUT @spatial
TO "/Output/ReferenceGuide/DDL/Assemblies/spatial.csv"
USING Outputters.Csv();
```

### See Also   
* [U-SQL Assemblies](u-sql-assemblies.md) 
* [CREATE ASSEMBLY (U-SQL)](create-assembly-u-sql.md)   
* [REFERENCE SYSTEM ASSEMBLY (U-SQL)](reference-system-assembly-u-sql.md)  
* [DROP ASSEMBLY (U-SQL)](drop-assembly-u-sql.md)  
* [USING Keyword](using-keyword.md)  
* [How to register U-SQL Assemblies in your U-SQL Catalog](https://blogs.msdn.microsoft.com/azuredatalake/2016/08/26/how-to-register-u-sql-assemblies-in-your-u-sql-catalog/)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md) 
* [U-SQL Programmability Guide](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide)

  
 
