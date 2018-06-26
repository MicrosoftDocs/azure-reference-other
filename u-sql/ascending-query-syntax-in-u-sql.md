---
title: "ascending (Query Syntax in U-SQL) | Microsoft Docs"
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

# ascending (Query Syntax in U-SQL)
The `ascending` contextual keyword is used in the [orderby](orderby-clause-query-syntax-in-u-sql.md) clause in query expressions to specify that the sort order is from smallest to largest. 

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
 
**Basic Example**   
```sql
// Dataset
DECLARE @fruits = new SQL.ARRAY<string>{"cherry", "apple", "blueberry"};

// Query
DECLARE @sortAscendingQuery =
            from fruit in @fruits
            orderby fruit ascending
            select fruit;

// Alternative native method
@result1b = 
        SELECT T.value AS nativeSort  
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@fruits) AS T(value)
        ORDER BY T.value ASC FETCH 3 ROWS;


@result1a = 
        SELECT T.value AS sortAscendingQuery              
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@sortAscendingQuery) AS T(value);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/ascending/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/ascending/example1b.txt"
USING Outputters.Tsv();
```

## See Also
* [orderby clause (Query Syntax in U-SQL)](orderby-clause-query-syntax-in-u-sql.md)
* [ascending (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/ascending)
* [OrderBy (Method Syntax in U-SQL)](orderby-method-syntax-in-u-sql.md)
* [OUTPUT: Order_By_Opt_Fetch_Clause (U-SQL)](output-statement-u-sql#OBOFC)
* [Enumerable.OrderBy (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.orderby)
* [orderby clause (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/orderby-clause)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)