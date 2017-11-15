---
title: "Calling a Procedure (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-06-29"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 99001354-3702-41da-a540-413266a4486b
caps.latest.revision: 9
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Calling a Procedure (U-SQL)
A procedure can be called inside a script or procedure and will be inlined into the execution graph before executing it. The invocation is similar to a table-valued function invocation with the difference that no rowset variable is being assigned.  The compiler does not allow more than 50 nested procedure calls to prevent stack overflow; please make sure that procedures are called with less nesting.
  
<table><th align="left">Syntax</th><tr><td><pre>
Procedure_Call :=                                                                                        
    <a href="#Ident">Identifier</a> '(' [<a href="#arg_lst">Argument_List</a>] ')'.<br />
<a href="#arg_lst">Argument_List</a> :=  
    Argument {',' Argument}.<br />  
Argument :=  
    argument_expression  
|   'DEFAULT'.
</pre></td></tr></table>
  
### Semantics of Syntax Elements    
-   <a name="Ident"></a>**`Identifier`**   
    Specifies the name of the called procedure. If the procedure name is a fully-specified three-part name, the procedure in the specified database and schema will be called. If the name is a two-part name, the procedure will be called in the current database context and specified schema. If the name is a simple identifier, then the procedure will be called in the current database and schema context.  
  
    If the procedure is not found or the user has no right to call it, an error is raised.  
  
-   <a name="arg_lst"></a>**`Argument_List`**   
    A procedure may take parameters for which values need to be provided. Unlike C# functions, one does not specify the parameter name when passing the argument values. Instead the values are assigned positionally to the parameters. One can either provide values using an expression or one can use the `DEFAULT` keyword to have the parameter’s default value chosen. Any expression passed to a parameter will be inlined in the function’s body. This means that non-deterministic expressions are not made deterministic by U-SQL; they will still be non-deterministic if they are invoked more than once by the final script unless they are known to be non-deterministic to U-SQL.  
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://channel9.msdn.com/Series/AzureDataLake/USQL-LocalRun).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples utilize the procedures created from [CREATE PROCEDURE (U-SQL)](../u-sql/create-procedure-u-sql.md).
```
// This example will call the procedure myFirstStoredProc:
TestReferenceDB.dbo.myFirstStoredProc();


// This example will call the procedure myStoredProcWithParameters:
TestReferenceDB.dbo.myStoredProcWithParameters  
(  
    200,  
    DateTime.Parse("12/11/2013")   
); 


// These two examples will call the procedure getPeople:
// Using default value for @filePath
TestReferenceDB.dbo.getPeople((new SQL.ARRAY<int>{100, 300, 800}), DEFAULT); 

// Specifying value for @filePath
TestReferenceDB.dbo.getPeople((new SQL.ARRAY<int>{100, 300, 800}), "/Output/ReferenceGuide/DDL/Procedure/getPeople2.csv"); 
```

**Additional Example**   
* See [Procedure addPeople](../u-sql/create-type-u-sql.md#sproc_pass), a procedure that accepts a table type as a parameter.


### See Also
* [U-SQL Procedures](../u-sql/u-sql-procedures.md)  
* [CREATE PROCEDURE (U-SQL)](../u-sql/create-procedure-u-sql.md)  
* [DROP PROCEDURE (U-SQL)](../u-sql/drop-procedure-u-sql.md)  
  
