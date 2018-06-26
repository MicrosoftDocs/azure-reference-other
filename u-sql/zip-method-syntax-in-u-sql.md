---
title: "Zip (Method Syntax in U-SQL) | Microsoft Docs"
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

# Zip (Method Syntax in U-SQL)
Applies a specified function to the corresponding elements of two sequences, producing a sequence of the results.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Zip<TFirst, TSecond, TResult>(IEnumerable\<TFirst>, IEnumerable\<TSecond>, Func<TFirst, TSecond, TResult>)**  
Returns an IEnumerable\<T> that contains merged elements of two input sequences.  
The following code example demonstrates how to use the Zip<TFirst, TSecond, TResult> method to merge two sequences.
```sql
// Dataset
DECLARE @numbers = new SQL.ARRAY<int>{0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
DECLARE @moreNumbers = new SQL.ARRAY<int>{1, 3, 5, 7, 9};
DECLARE @words = new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"};

// Queries
DECLARE @zip = @numbers
              .Zip(@words, (first, second) => first + ", " + second);

DECLARE @zip2 = @numbers
              .Zip(@moreNumbers, (first, second) => first + " plus " + second + " equals: " + (first + second).ToString());

@result1 =
    SELECT T.value AS zip
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@zip) AS T(value);

@result2 =
    SELECT T.value AS zip
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@zip2) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Zip/example1.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Zip/example2.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Zip (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.zip)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 