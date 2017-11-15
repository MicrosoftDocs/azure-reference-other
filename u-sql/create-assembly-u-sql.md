---
title: "CREATE ASSEMBLY (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-04-13"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: da494f4a-ace2-4e74-bb40-188c6ca767de
caps.latest.revision: 17
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CREATE ASSEMBLY (U-SQL)
If a .NET assembly is required during script compilation (for example because it specifies a function or type that needs to be resolved during compile time), then it needs to be registered.  

The `CREATE ASSEMBLY` statement registers an assembly and optionally associated resources.  

<table><th align="left">Syntax</th><tr><td><pre>
Create_Assembly_Statement :=                                                                             
    'CREATE' 'ASSEMBLY' [<a href="#INE">'IF' 'NOT' 'EXISTS'</a>] <a href="#ass_name">Assembly_Name</a>  
    'FROM' <a href="#ass_src">Assembly_Source</a>   
    [<a href="#w_add_fl">'WITH' 'ADDITIONAL' 'FILES'</a> '='   
            '(' <a href="#ass_add_fl">Assembly_Additional_File_List</a> ')'].<br /> 
<a href="#ass_name">Assembly_Name</a> :=
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.<br />
<a href="#ass_src">Assembly_Source</a> :=
    <a href="expressions-u-sql.md">Static_String_Expression</a> | lexical_binary_value.</pre></td></tr></table>
   
### Semantics of Syntax Elements  
- <a name="ass_name"></a>**`Assembly_Name`**  
  Specifies the name of the assembly in the current database context.  
  
  If an object of the given name already exists in the specified database context or the user has no permissions to create an assembly, an error is raised.  
  
-   <a name="INE"></a>**`IF NOT EXISTS`**    
    If the optional `IF NOT EXISTS` is specified, then the statement creates the assembly registration if it does not already exist, or succeeds without changes if the assembly already exists and the user has permission to at least enumerate all existing assemblies.  
  
- <a name="ass_src"></a>**`Assembly_Source`**  
  Specifies the assembly DLL either in form of a binary literal or as a string literal or static string expression/string variable. The binary literal represents the actual .NET assembly DLL, while the string values represent a URI or file path to a .NET assembly DLL file in either an accessible Azure Data Lake Storage or Windows Azure Blob Storage. If the provided source is a valid .NET assembly, the assembly will be copied and registered, otherwise an error is raised.  A database cannot contain more than one version of the same assembly.
    
  Note that the binary literal is mainly useful for tools that want to register the assembly without first creating and then copying a file.  
  
 <a name="w_add_fl"></a> 
- <a name="ass_add_fl"></a>**`Assembly_Additional_File_List`**  
  Optionally, additional files can be provided in the <a name="w_add_fl"></a>WITH ADDITIONAL FILES clause:  
  
  <table><th>Syntax</th><tr><td><pre>
  <a href="#ass_add_fl">Assembly_Additional_File_List</a> :=                                                                    
      <a href="#ass_add_f">Assembly_Additional_File</a> {',' <a href="#ass_add_f">Assembly_Additional_File</a>}.<br />                                                                                                    
  <a href="#ass_add_f">Assembly_Additional_File</a> :=  
      <a href="#ass_src">Assembly_Source</a> [<a href="#str_lit">'AS' string_literal</a>].</pre></td></tr></table>
 
  An additional file is specified with:   
  
  - <a name="ass_add_f"></a>**`Assembly_Additional_File`**   
    Each additional file can be represented in the same way as the main assembly by either referring to a file location or the actual file content in binary format. The file can be any type of file that may be needed in conjunction with the main assembly. Some general use cases are: configuration text, JSON or XML files, native DLLs or executables that are called by the code in the assembly.  
  
    Other .NET assembly files can be added, as long as they are only needed during runtime and not script compilation, although it is not recommended. If they are needed during compilation, they have to be separately registered with CREATE ASSEMBLY and referenced in the script with [REFERENCE ASSEMBLY](../USQL/reference-assembly-u-sql.md). Note that an additionally added .NET assembly may conflict with an explicitly referenced assembly in the same script, so care has to be taken when deciding to include a .NET assembly file as an additional file.  
  
  - <a name="str_lit"></a>**`'AS' string_literal`**   
    This clause optionally specifies the name that is used for the additional file, when it is placed into the runtime working directory. The string literal has to be a valid filename (and not contain a path) or an error is raised. Note that this should the name of the file that the main assembly will be using to refer to the file or the assembly code will fail to find the file at runtime and raise an error.  
  
### Example  
1. Download and install `ENU\x64\SQLSysClrTypes.msi` 
from [Microsoft® SQL Server® 2016 Feature Pack](https://www.microsoft.com/en-us/download/details.aspx?id=52676).

2. Create directory `upload\asm\spatial` in your Azure Data Lake Store.  Upload the following files to `upload\asm\spatial`:
    * `C:\Program Files (x86)\Microsoft SQL Server\130\SDK\Assemblies\Microsoft.SqlServer.Types.dll`
    * `C:\Windows\System32\SqlServerSpatial130.dll`

3. Register assembly
```
DECLARE @ASSEMBLY_PATH string = "/upload/asm/spatial/";
DECLARE @SPATIAL_ASM string = @ASSEMBLY_PATH+"Microsoft.SqlServer.Types.dll";
DECLARE @SPATIAL_NATIVEDLL string = @ASSEMBLY_PATH+"SqlServerSpatial130.dll";

CREATE DATABASE IF NOT EXISTS SQLSpatial;
USE DATABASE SQLSpatial;

DROP ASSEMBLY IF EXISTS SqlSpatial;
CREATE ASSEMBLY SqlSpatial
FROM @SPATIAL_ASM
WITH ADDITIONAL FILES =
     (
         @SPATIAL_NATIVEDLL
    );
```
  
### See Also    
* [U-SQL Assemblies](../USQL/u-sql-assemblies.md)
* [REFERENCE ASSEMBLY (U-SQL)](../USQL/reference-assembly-u-sql.md)  
* [REFERENCE SYSTEM ASSEMBLY (U-SQL)](../USQL/reference-system-assembly-u-sql.md)  
* [DROP ASSEMBLY (U-SQL)](../USQL/drop-assembly-u-sql.md)  
* [Extending U-SQL Expressions with User-Code](../USQL/extending-u-sql-expressions-with-user-code.md) 
* [How to register U-SQL Assemblies in your U-SQL Catalog](https://blogs.msdn.microsoft.com/azuredatalake/2016/08/26/how-to-register-u-sql-assemblies-in-your-u-sql-catalog/)
 * [U-SQL Programmability Guide](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide)

