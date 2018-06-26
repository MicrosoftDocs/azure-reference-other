---
title: "Last (Method Syntax in U-SQL) | Microsoft Docs"
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

# Last (Method Syntax in U-SQL)
Returns the last element of a sequence.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset(s) defined below. 

**Dataset**  
```sql
@table = 
SELECT * FROM 
    ( VALUES
    (new SQL.ARRAY<int>{1, 2, 3, 4, 5, 6, 7, 8, 9, 0}, 
            new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"})
    ) AS T(numbers, words);
```

**Last\<TSource>(IEnumerable\<TSource>)**  
Returns the value at the last position in the source sequence.
The following code example demonstrates how to use Last\<TSource>(IEnumerable\<TSource>) to return the last element of an array.
```sql
@result1 =
    SELECT 
        numbers.Last() AS Last_numbers,
        words.Last() AS Last_words
    FROM @table;

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Last/example1.txt"
USING Outputters.Tsv();
```

**Last\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>)**  
Returns the last element in a sequence that satisfies a specified condition.  
The following code example demonstrates how to use Last\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>) to return the last element of an array that satisfies a condition.
```sql
@result2 =
    SELECT 
        words.Last(x => x.Length > 4) AS Last_words
    FROM @table;

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Last/example2.txt"
USING Outputters.Tsv();
```


## See Also
* [Enumerable.Last (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.last)
* [LastOrDefault (Method Syntax in U-SQL)](lastordefault-method-syntax-in-u-sql.md)
* [First (Method Syntax in U-SQL)](first-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 