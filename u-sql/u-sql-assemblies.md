---
title: "U-SQL Assemblies | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 12d8bae5-1df7-447a-9a6a-2d6e8f734fd0
caps.latest.revision: 19
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Assemblies
One of the major value propositions and design goals of U-SQL is to provide an easy to use and powerful way to [extend U-SQL with custom user code](extending-u-sql-expressions-with-user-code.md). The main aspects that are enabling these goals are the [C#-based U-SQL type system](data-types-and-literals-u-sql.md) and [U-SQL’s expression language](expressions-u-sql.md).  
  
U-SQL provides the ability to use .NET assemblies in U-SQL’s metadata catalog in order to encapsulate more complex expressions into [user-defined functions](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-functions---udf), and to extend the processing capabilities of U-SQL with [user-defined aggregators](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-aggregates--udagg) or [user-defined operators](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-objects--udo) (UDOs). If a .NET assembly is required during script compilation (for example because it specifies a function or type that needs to be resolved during compile time), then it needs to be registered with [CREATE ASSEMBLY](create-assembly-u-sql.md) and the referenced with [REFERENCE ASSEMBLY](reference-assembly-u-sql.md).  

U-SQL provides the [CREATE ASSEMBLY](create-assembly-u-sql.md) and [DROP ASSEMBLY](drop-assembly-u-sql.md) statements to manage the assembly DLL registration. Assemblies are scoped to a U-SQL database.  
  
It also provides the ability to reference assemblies, both user-defined and system defined assemblies with the [REFERENCE ASSEMBLY](reference-assembly-u-sql.md) statement.   
  
<table><th align="left">Syntax</th><tr><td><pre>
Assembly_DDL_Statement :=                                                                                
     <a href="create-assembly-u-sql.md">Create_Assembly_Statement</a>  
|    <a href="drop-assembly-u-sql.md">Drop_Assembly_Statement</a>.<br />
Reference_Assembly_Statement :=  
     <a href="reference-assembly-u-sql.md">Reference_User_Assembly_Statement</a>   
|    <a href="reference-system-assembly-u-sql.md">Reference_System_Assembly_Statement</a>.
</pre></td></tr></table>

### See Also    
* [CREATE ASSEMBLY (U-SQL)](create-assembly-u-sql.md)  
* [REFERENCE ASSEMBLY (U-SQL)](reference-assembly-u-sql.md)  
* [REFERENCE SYSTEM ASSEMBLY (U-SQL)](reference-system-assembly-u-sql.md)  
* [DROP ASSEMBLY (U-SQL)](drop-assembly-u-sql.md)  
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)  
* [U-SQL Programmability Guide](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide)  
* [How to register U-SQL Assemblies in your U-SQL Catalog](https://blogs.msdn.microsoft.com/azuredatalake/2016/08/26/how-to-register-u-sql-assemblies-in-your-u-sql-catalog/)
* [Develop U-SQL assemblies for Azure Data Lake Analytics jobs](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-develop-assemblies)
 
