---
title: "LINQ Inline Usage in U-SQL | Microsoft Docs"
ms.custom: ""
ms.date: "07/01/2018"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 
caps.latest.revision: 
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# LINQ Inline Usage in U-SQL
Language-Integrated Query (LINQ) is the name for a set of technologies based on the integration of query capabilities directly into the C# language. 

Most queries in the introductory (LINQ) documentation are written by using the LINQ declarative query syntax. However, the query syntax must be translated into method calls for the .NET common language runtime (CLR) when the code is compiled. These method calls invoke the standard query operators, which have names such as `Where`, `Select`, and `Average`. You can call them directly by using method syntax instead of query syntax.

Query syntax and method syntax are semantically identical, but many people find query syntax simpler and easier to read. Some queries must be expressed as method calls. For example, you must use a method call to express a query that retrieves the number of elements that match a specified condition. You also must use a method call for a query that retrieves the element that has the maximum value in a source sequence. The reference documentation for the standard query operators in the [System.Linq](https://docs.microsoft.com/dotnet/api/system.linq) namespace generally uses method syntax. Therefore, even when getting started writing LINQ queries, it is useful to be familiar with how to use method syntax in queries and in query expressions themselves. 

* [Query Syntax in U-SQL](query-syntax-in-u-sql.md)
* [Method Syntax in U-SQL](method-syntax-in-u-sql.md)

## See Also 
* [Language Integrated Query (LINQ)](https://docs.microsoft.com/dotnet/csharp/linq/index) 
* [LINQ (Language Integrated Query)](https://docs.microsoft.com/en-us/dotnet/standard/using-linq)
* [Query Syntax and Method Syntax in LINQ (C#)](https://docs.microsoft.com/dotnet/csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq)
* [System.Linq Namespace](https://docs.microsoft.com/dotnet/api/system.linq)

