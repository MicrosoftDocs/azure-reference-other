---
title: "LastOrDefault (Method Syntax in U-SQL) | Microsoft Docs"
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

# LastOrDefault (Method Syntax in U-SQL)
Returns the last element of a sequence, or a default value if no element is found.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset(s) defined below. 

**Dataset**  
```sql
@table = 
SELECT * FROM 
    ( VALUES
    (new SQL.ARRAY<int>{}, new SQL.ARRAY<int>{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}, 
            new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"})
    ) AS T(empty, nonEmpty, words);
```

**LastOrDefault\<TSource>(IEnumerable\<TSource>)**  
Returns the last element of a sequence, or a default value if the sequence contains no elements.  
The following code example demonstrates how to use LastOrDefault\<TSource>(IEnumerable\<TSource>) on an empty array.
```sql
@result1 =
    SELECT  empty.LastOrDefault() AS LastOrDefault_empty,
            empty.DefaultIfEmpty(1).Last() AS DefaultIfEmpty,   // Contrast with LastOrDefault
            nonEmpty.LastOrDefault() AS LastOrDefault_nonEmpty
    FROM @table;

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/LastOrDefault/example1.txt"
USING Outputters.Tsv();
```

**LastOrDefault\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>)**  
Returns the last element of a sequence that satisfies a condition or a default value if no such element is found.  
The following code example demonstrates how to use LastOrDefault\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>) by passing in a predicate. In the second call to the method, there is no element in the sequence that satisfies the condition.
```sql
@result2 =
    SELECT  words.LastOrDefault(x => x.Length > 4) AS LastOrDefault
    FROM @table;

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/LastOrDefault/example2.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.LastOrDefault (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.lastordefault)
* [Last (Method Syntax in U-SQL)](last-method-syntax-in-u-sql.md)
* [First (Method Syntax in U-SQL)](first-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)