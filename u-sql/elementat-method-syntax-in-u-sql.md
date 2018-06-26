---
title: "ElementAt (Method Syntax in U-SQL) | Microsoft Docs"
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

# ElementAt (Method Syntax in U-SQL)
Returns the element at a specified index in a sequence.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**ElementAt\<TSource>(IEnumerable\<TSource>, Int32)**  
The following code example demonstrates how to use ElementAt\<TSource> to return an element at a specific position.
```sql
// Dataset
@table = 
SELECT * FROM 
    ( VALUES
    (new SQL.ARRAY<int>{1, 2, 3, 4, 5, 6, 7, 8, 9, 0}, 
            new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"})
    ) AS T(numbers, words);

//Query
@result1 =
    SELECT  numbers.ElementAt(0) AS Element_first,
            words.ElementAt(1) AS Element_second
    FROM @table;

// Alternative native method
@result1a =
    SELECT  numbers[0] AS Native_first,
            words[1] AS Native_second
    FROM @table;

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Element/example1.txt"
USING Outputters.Tsv();

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Element/example1a.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.ElementAt (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.elementat)
* [Enumerable.ElementAtOrDefault (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.elementatordefault)
* [ElementAtOrDefault (Method Syntax in U-SQL)](elementatordefault-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 