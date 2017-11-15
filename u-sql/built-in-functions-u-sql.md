---
title: "Built-in Functions (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: f2c5fd54-3307-40ee-a2b6-8e5ccd31339c
caps.latest.revision: 16
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Built-in Functions (U-SQL)
While U-SQL is using C# as its expression language and thus has a large set of the Common Language Runtime (CLR) libraries and all of C#’s operators at the user’s disposal, it also adds a couple of common Built-in U-SQL Functions.

### Types of Functions   
|Function|Description|
|----|--|
|[Aggregate Functions](../USQL/aggregate-functions-u-sql.md)|An aggregator will compute a single result value over a group of values and will have an identity value for the case that the group is empty.|  
|[Analytic Functions](../USQL/analytic-functions-u-sql.md)|Analytic functions compute an aggregate value based on a group of rows. However, unlike aggregate functions, they can return multiple rows for each group.|
|[Metadata Functions](../USQL/metadata-functions-u-sql.md)|Returns information about the database and database objects.|
|[Ranking Functions](../USQL/ranking-functions-u-sql.md)|Returns a ranking value for each row in a partition.|
|[Built-in U-SQL UDOs](../USQL/built-in-u-sql-udos.md)|Provides extraction from and outputting to some common data formats. |
  
### See Also    
* [U-SQL Language Reference](../USQL/u-sql-language-reference.md) 
* [Built-in U-SQL UDOs](../USQL/built-in-u-sql-udos.md)
