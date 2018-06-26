---
title: "Skip (Method Syntax in U-SQL) | Microsoft Docs"
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

# Skip (Method Syntax in U-SQL)
Bypasses a specified number of elements in a sequence and then returns the remaining elements.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Skip\<TSource>(IEnumerable\<TSource>, Int32)**  
The following code example demonstrates how to use Skip\<TSource> to skip a specified number of elements in a sorted array and return the remaining elements.
```sql
// Dataset
@table = 
SELECT * FROM 
    ( VALUES
    ( new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"})
    ) AS T(words);

@result1 =
    SELECT T.value AS skip3
    FROM  @table
    CROSS APPLY EXPLODE (words.Skip(3)) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Skip/example1.txt"
USING Outputters.Tsv();


// contrast with Take
@result2 =
    SELECT T.value AS take3
    FROM  @table
    CROSS APPLY EXPLODE (words.Take(3)) AS T(value);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Skip/example2.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Skip (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.skip)
* [SkipWhile (Method Syntax in U-SQL)](skipwhile-method-syntax-in-u-sql.md)
* [Take (Method Syntax in U-SQL)](take-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)