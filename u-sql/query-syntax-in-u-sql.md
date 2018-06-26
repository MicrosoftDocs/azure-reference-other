---
title: "Query Syntax in U-SQL | Microsoft Docs"
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

# Query Syntax in U-SQL
This section contains the contextual keywords used in query expressions. 


## In This Section    
|Keyword|Description|  
|------------|-----------------|  
|[from](from-clause-query-syntax-in-u-sql.md)|Specifies a data source and a range variable (similar to an iteration variable).|  
|[where](where-clause-query-syntax-in-u-sql.md)|Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).|  
|[select](select-clause-query-syntax-in-u-sql.md)|Specifies the type and shape that the elements in the returned sequence will have when the query is executed.|  
|[group](group-clause-query-syntax-in-u-sql.md)|Groups query results according to a specified key value.|  
|[into](into-query-syntax-in-u-sql.md)|Provides an identifier that can serve as a reference to the results of a join, group or select clause.|  
|[orderby](orderby-clause-query-syntax-in-u-sql.md)|Sorts query results in ascending or descending order based on the default comparer for the element type.|  
|[join](join-clause-query-syntax-in-u-sql.md)|Joins two data sources based on an equality comparison between two specified matching criteria.|  
|[let](let-clause-query-syntax-in-u-sql.md)|Introduces a range variable to store sub-expression results in a query expression.|  
|[on](on-query-syntax-in-u-sql.md)|Contextual keyword in a [join](join-clause-query-syntax-in-u-sql.md) clause.|  
|[equals](equals-query-syntax-in-u-sql.md)|Contextual keyword in a [join](join-clause-query-syntax-in-u-sql.md) clause.|  
|[by](by-query-syntax-in-u-sql.md)|Contextual keyword in a [group](group-clause-query-syntax-in-u-sql.md) clause.|  
|[ascending](ascending-query-syntax-in-u-sql.md)|Contextual keyword in an [orderby](orderby-clause-query-syntax-in-u-sql.md) clause.|  
|[descending](descending-query-syntax-in-u-sql.md)|Contextual keyword in an [orderby](orderby-clause-query-syntax-in-u-sql.md) clause.|  


## See Also
* [Method Syntax in U-SQL](method-syntax-in-u-sql.md)
* [Query Keywords (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/query-keywords)
* [Standard Query Operators Overview (C#)](https://docs.microsoft.com/dotnet/csharp/programming-guide/concepts/linq/standard-query-operators-overview)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)