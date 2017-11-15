---
title: "Table-Valued Function Expression (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-17"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 56e65ade-f69c-4897-9593-50ac1b9099e8
caps.latest.revision: 17
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Table-Valued Function Expression (U-SQL)
U-SQL allows table-valued functions (TVF) to be called as primary rowset expressions even outside of a SELECT’s [FROM](../USQL/from-clause-u-sql.md) clause. Note that the statements that make up the definition of a U-SQL Table-valued function are always inlined where they are called, while preserving the visibility rules of the context.  For more information, see [U-SQL Table-valued Functions](../USQL/u-sql-table-valued-functions.md).  
  
A U-SQL TVF can either return a single rowset or multiple rowsets. If it returns multiple rowsets it can only be assigned to rowset variables and cannot be called in a [FROM](../USQL/from-clause-u-sql.md) clause, set expressions, or [OUTPUT](../USQL/output-statement-u-sql.md) .  
  
<table><th align="left">Syntax</th><tr><td><pre>
Function_Call :=                                                                                         
     <a href="#Ident">Identifier</a> '(' [<a href="#arg_lst">Argument_List</a>] ')'.<br />
<a href="#arg_lst">Argument_List</a> :=
     Argument {',' Argument}.<br />
Argument :=
     argument_expression  
|    'DEFAULT'.
</pre></td></tr></table>
  
### Semantics of Syntax Elements  
- <a name="Ident"></a>**`Identifier`**   
The identifier invokes the table-valued function (TVF) of the given name. If the function name is a fully-specified three-part name, the function in the specified database and schema will be called. If the name is a two-part name, the function will be called in the current database context and specified schema. If the name is a simple identifier, then the function will be called in the current database and schema context. If the function is not found, an error is raised.  
  
- <a name="arg_lst"></a>**`Argument_List`**   
  A function may take optional arguments for which values need to be provided. Unlike C# functions, one does not specify the argument name. Instead the values are assigned positionally to the arguments. One can either provide values using an argument expression or one can use the DEFAULT keyword to have the argument’s default value chosen.  
  
  Any expression passed to a TVF argument will be inlined in the function’s body. This means that non-deterministic expressions are not made deterministic by U-SQL; they will still be non-deterministic if they are invoked more than once by the final query.  
  
  Argument expressions are limited to constant-foldable expressions  and references to columns and rowset variables.  
  
### Examples   
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The examples below use the sample data provided with your Data Lake Analytics account. See [Prepare source data](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-get-started-portal#prepare-source-data) for additional information.

The calls below are for the functions created at [CREATE FUNCTION (U-SQL): Table-valued Function](../USQL/create-function-u-sql-table-valued-function.md).
```
USE TestReferenceDB;

// Calling SearchLog
OUTPUT dbo.SearchLog()  
TO "/Output/ReferenceGuide/DDL/Functions/callSearchlog.csv"
USING Outputters.Csv();  


// Calling SearchLogPerRegion
@SearchLogPerRegion = dbo.SearchLogPerRegion(DEFAULT);  
OUTPUT @SearchLogPerRegion  
TO "/Output/ReferenceGuide/DDL/Functions/callSearchLogPerRegionA1.csv"
USING Outputters.Csv();  

// Calling SearchLogPerRegion and using ORDER BY with FETCH
@SearchLogPerRegion = dbo.SearchLogPerRegion(DEFAULT) ORDER BY Start DESC FETCH 1 ROWS;  
OUTPUT @SearchLogPerRegion  
TO "/Output/ReferenceGuide/DDL/Functions/callSearchLogPerRegionA2.csv"
USING Outputters.Csv();  

// Calling SearchLogPerRegion
OUTPUT dbo.SearchLogPerRegion("en-us")  
TO "/Output/ReferenceGuide/DDL/Functions/callSearchLogPerRegionB.csv"
USING Outputters.Csv();  


// Calling SearchLogPerRegionWithRemainder
(@definedRegion, @remainderRegions) = SearchLogPerRegionWithRemainder("en-us");
// First result set
OUTPUT @definedRegion
TO "/Output/ReferenceGuide/DDL/Functions/SearchLogPerRegionWithRemainderA.csv"
USING Outputters.Csv();  

// Second result set
@result = 
    SELECT * FROM @remainderRegions
    WHERE Query == "microsoft";
    
OUTPUT @result
TO "/Output/ReferenceGuide/DDL/Functions/SearchLogPerRegionWithRemainderB.csv"
USING Outputters.Csv();  
```
  
### See Also 
* [Query Statements and Expressions (U-SQL)](../USQL/query-statements-and-expressions-u-sql.md)   
* [Output Statement (U-SQL)](../USQL/output-statement-u-sql.md) 
* [U-SQL Functions](../USQL/u-sql-functions.md) 


