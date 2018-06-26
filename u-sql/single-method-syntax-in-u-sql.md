---
title: "Single (Method Syntax in U-SQL) | Microsoft Docs"
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

# Single (Method Syntax in U-SQL)
Returns a single, specific element of a sequence.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**Single\<TSource>(IEnumerable\<TSource>)**  
Returns the only element of a sequence, and throws an exception if there is not exactly one element in the sequence.  
Note that an `ArgumentNullException` exception is not thrown when the sequence contains a null value  
The following code example demonstrates how to use Single\<TSource>(IEnumerable\<TSource>) to select the only element of an array.
```sql
// Dataset
@table = 
SELECT * FROM 
    ( VALUES
    (new SQL.ARRAY<int>{3}, new SQL.ARRAY<int?>{null}, new SQL.ARRAY<int>(), new SQL.ARRAY<int>{1, 2, 3, 4}) 
    ) AS T(col1, col2, col3, col4);

// Query
@result1 =
    SELECT col1.Single() AS single,
           col2.Single() AS singleNull
           //, col3.Single() AS singleEmpty         // will error; InvalidOperationException
           //, col4.Single() AS singleMultiple      // will error; InvalidOperationException
    FROM @table;

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Single/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Single\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>)**  
Returns the only element of a sequence that satisfies a specified condition, and throws an exception if more than one such element exists.
```sql
// Dataset
DECLARE @words = new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"};

// Query
@result2 =
    SELECT @words.Single(x => x.Length > 5) AS singleFunc
    FROM (VALUES(1)) AS A(x);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Single/example2.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Single (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.single)
* [SingleOrDefault (Method Syntax in U-SQL)](singleordefault-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 