---
title: "CREATE PACKAGE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "05/05/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 1c259ca8-5d7b-4b5f-89ef-70125034070f
caps.latest.revision: 3
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CREATE PACKAGE (U-SQL)
The `CREATE PACKAGE` statement creates a package to allow bundling of commonly used together U-SQL [assemblies](u-sql-assemblies.md), [variables](variables-u-sql.md) and resources.

A package declaration can consist of the using statement, and declare statements to set its own internal static name context, import from other packages, declare what gets exported by the package, and what resources the package will deploy to the runtime vertices. It also provides an IF statement that has the same semantics as the general U-SQL IF statement but only allows the statements supported inside a package definition.

The optional parameters can be used inside the package definition to help define variables, and to determine which alternative the IF statement will choose.

The package object will be created inside the current database and schema context.

<table><th align="left">Syntax</th><tr><td><pre>
Create_Package_Statement :=                                                                              
    'CREATE' 'PACKAGE' [<a href="#INE">'IF' 'NOT' 'EXISTS'</a>] <a href="#Ident">Identifier</a> '(' [<a href="#param_lst">Parameter_List</a>] ')'
    ['AS']
    'BEGIN'
        Package_Statement_List
    'END'.<br />
Package_Statement_List := 
    { Package_Statement }.<br />
Package_Statement :=
    Using_Statement
|   Declare_Variable_Statement
|   <a href="import-package-u-sql.md">Import_Package_Statement</a>
|   Export_Statement
|   Deploy_Resource_Statement
|   If_Package_Statement.<br />
Export_Statement :=
    <a href="#exp_ass">Export_User_Assembly_Statement | Export_System_Assembly_Statement</a> | <a href="#exp_var">Export_Variable_Statement</a>.<br />
If_Package_Statement :=
    'IF' <a href="#bool_expr">Boolean_Expression</a> 'THEN'
        Package_Statement
    ['ELSEIF' <a href="#bool_expr">Boolean_Expression</a> 'THEN'
        Package_Statement ]
    ['ELSE' <a href="#bool_expr">Boolean_Expression</a> 'THEN'
        Package_Statement ]
    'END'.
</pre></td></tr></table>


### Semantics of Syntax Elements  
- <a name="INE"></a>**`IF NOT EXISTS`**    
  If the optional `IF NOT EXISTS` is specified, then the statement creates the package if it does not already exist, or succeeds without changes if the package already exists and the user has permission to at least enumerate all existing packages. 
    
- <a name="Ident"></a>**`Identifier`**   
  Specifies the name of the package. If the `Identifier` is a three-part identifier, the package will be created in the specified database and schema. If it is a two-part identifier, then the package will be created in the specified schema of the current database context. If the identifier is a simple identifier, then the package will be created in the current database and schema context.  
  
    If an object of the given name already exists in the specified database and schema context or the user has no permissions to create a package, an error is raised.  
    
-   <a name="param_lst"></a>**`Parameter_List`**    
    The parameter list provides the arguments and their types and optional default values.
    
- <a name="bool_expr"></a>**`Boolean_Expression`**  
Is a constant-foldable expression that returns TRUE or FALSE.   

- <a name="exp_ass"></a>**`Export_User_Assembly_Statement | Export_System_Assembly_Statement`**  
  The `EXPORT ASSEMBLY` and `EXPORT SYSTEM ASSEMBLY` statements specify inside a package definition which user or system assemblies respectively are being exported by the package. They also implicitly reference the assembly for the package context.    

  The identifier will be resolved in the static context of the package definition, similarly to table-valued functions and procedures and can refer optionally to a user assembly in a different Azure Data Lake Analytics account.   
  
  <table><th>Syntax</th><tr><td><pre>
  Export_User_Assembly_Statement :=                                                                   
      'EXPORT' 'ASSEMBLY' <a href="reference-assembly-u-sql.md#ass_name">Global_Assembly_Identifier</a>.<br />
  Export_System_Assembly_Statement :=
      'EXPORT' 'SYSTEM' 'ASSEMBLY' <a href="create-assembly-u-sql.md#ass_name">Assembly_Name</a>.<br />
  Assembly_Name := 
      <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
  </pre></td></tr></table>       

- <a name="exp_var"></a>**`Export_Variable_Statement`**  
  The `EXPORT` statement specifies inside a package definition which variable is being exported by the package. It also implicitly declares the variable inside the package context.

  <table><th>Syntax</th><tr><td><pre>
  Export_Variable_Statement :=                                                                        
      'EXPORT' ['CONST'] User_Variable_Name [Scalar_Type] '=' csharp_expression.<br />
  User_Variable_Name :=
      "@"+<a href="u-sql-identifiers.md">Unquoted_Identifier</a>.<br />   
  Scalar_Type := 
      <a href="built-in-u-sql-types.md">Built_in_Type</a> | <a href="https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-user-defined-types---udt">User_defined_Type</a>.
  </pre></td></tr></table>

  If a variable of a user-defined type gets exported, then the assembly defining the type should also be exported.

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Basic Syntax**  
The following example creates a package XMLFiles in an already existing database `TestReferenceDB`. The package exports a variable named `@xmlfile` with the value `/configfiles/config.xml` and deploys that file. The file does not need to exist during creation of the package, but it will have to exist at the time the import of the package occurs into the main script.
```sql
USE DATABASE TestReferenceDB;
DROP PACKAGE IF EXISTS XMLFiles;

CREATE PACKAGE XMLFiles()
BEGIN
    EXPORT @xmlfile = "/configfiles/config.xml";
    DEPLOY RESOURCE @xmlfile;
END;
```

**Parameterized package**   
A parameterized package, `XMLorJSON`, is created in the same database that - based on the passed parameter - bundles the previously created custom assembly `Microsoft.Analytics.Samples.Formats` from the database `JSONBlog` with a different assembly (`NewtonSoft.Json` from the database `JSONBlog` if the parameter is `json` or the system assembly `System.Xml` if the parameter is `xml`) and a `@format` variable, that is set to different values depending on the parameter. It also imports the previously defined package `XMLFiles` with the alias `xmlpack` and re-exports its `@xmlfile` variable if the parameter is set to `xml`.
```sql
DROP PACKAGE IF EXISTS TestReferenceDB.dbo.XMLorJSON;

CREATE PACKAGE TestReferenceDB.dbo.XMLorJSON(@requestedFormat string = "json")
BEGIN
    // @xml and @json are just used inside the package and are not exported
    DECLARE @xml = "xml";
    DECLARE CONST @json = "json"; 

    // The following IMPORT statements will import variables and resource deployments from XMLFiles. 
    // Since there is no automatic re-export, it does not make sense to put an assembly export into
    // a package that only gets imported into a different package.
    // Note that no argument list is needed if no arguments are being passed.

    IF @requestedFormat == @xml THEN 
        IMPORT PACKAGE XMLFiles AS xmlpack;

        EXPORT ASSEMBLY JSONBlog.[Microsoft.Analytics.Samples.Formats];
        EXPORT SYSTEM ASSEMBLY [System.Xml]; 
        EXPORT @xmlfile = xmlpack.@xmlfile;
        EXPORT @format = "xml";

    ELSEIF @requestedFormat == @json THEN
        EXPORT ASSEMBLY JSONBlog.[Microsoft.Analytics.Samples.Formats];
        EXPORT ASSEMBLY [NewtonSoft.Json];
        EXPORT @format = "json";

    ELSE
        EXPORT @format = "invalid";
    END;
END;
```

### See Also
* [DROP PACKAGE (U-SQL)](drop-package-u-sql.md)  
* [IMPORT PACKAGE (U-SQL)](import-package-u-sql.md)
