---
title: "First (Method Syntax in U-SQL) | Microsoft Docs"
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

# First (Method Syntax in U-SQL)
Returns the first element of a sequence.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset(s) defined below.

**Dataset**  
```
@table = 
SELECT * FROM 
    ( VALUES
    ( new SQL.ARRAY<int>{1, 2, 3, 4, 5, 6, 7, 8, 9, 0}, 
            new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"})
    ) AS T(numbers, words);
```

**First\<TSource>(IEnumerable\<TSource>)**  
The following code example demonstrates how to use First<TSource>(IEnumerable<TSource>) to return the first element of an array.
```sql
@result1 =
    SELECT numbers.First() AS First_numbers,
           words.First() AS First_words
    FROM @table;

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/First/example1.txt"
USING Outputters.Tsv();
```

**First\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>)**  
Returns the first element in a sequence that satisfies a specified condition.  
The following code example demonstrates how to use First\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>) to return the first element of an array that satisfies a condition.
```sql
@result2 =
    SELECT words.First(x => x.Length > 5) AS First_words
    FROM @table;

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/First/example2.txt"
USING Outputters.Tsv();
```


## See Also
* [Enumerable.First (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.first)
* [Enumerable.FirstOrDefault (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.firstordefault)
* [FirstOrDefault (Method Syntax in U-SQL)](firstordefault-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 