---
title: "FirstOrDefault (Method Syntax in U-SQL) | Microsoft Docs"
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

# FirstOrDefault (Method Syntax in U-SQL)
Returns the first element of a sequence, or a default value if no element is found.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset(s) defined below.

**Dataset**   
```sql
@table = 
SELECT * FROM 
    ( VALUES
    (new SQL.ARRAY<int>{}, new SQL.ARRAY<int>{1, 2, 3, 4, 5, 6, 7, 8, 9, 0}, 
            new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"})
    ) AS T(empty, nonEmpty, words);
```

**FirstOrDefault\<TSource>(IEnumerable\<TSource>)**   
Returns the first element of a sequence, or a default value if the sequence contains no elements.  
The following code example demonstrates how to use FirstOrDefault\<TSource>(IEnumerable\<TSource>) on an empty array.
```sql
@result1 =
    SELECT  empty.FirstOrDefault() AS FirstOrDefault_empty,
            empty.DefaultIfEmpty(1).First() AS DefaultIfEmpty,   // Contrast with FirstOrDefault
            nonEmpty.FirstOrDefault() AS FirstOrDefault_nonEmpty
    FROM @table;

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/FirstOrDefault/example1.txt"
USING Outputters.Tsv();
```

**FirstOrDefault\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>)**    
Returns the first element of the sequence that satisfies a condition or a default value if no such element is found.  
The following code example demonstrates how to use FirstOrDefault\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>) by passing in a predicate. 
```sql
@result2 =
    SELECT  words.FirstOrDefault(x => x.Length > 5) AS FirstOrDefault,
            words.FirstOrDefault(x => x.Length > 15) AS FirstOrDefault_empty
    FROM @table;

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/FirstOrDefault/example2.txt"
USING Outputters.Tsv(outputHeader: true);
```

## See Also
* [Enumerable.FirstOrDefault (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.firstordefault)
* [Enumerable.First (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.first)
* [First (Method Syntax in U-SQL)](first-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 