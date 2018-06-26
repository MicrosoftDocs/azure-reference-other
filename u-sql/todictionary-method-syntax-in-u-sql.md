---
title: "ToDictionary (Method Syntax in U-SQL) | Microsoft Docs"
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

# ToDictionary (Method Syntax in U-SQL)
Creates a [Dictionary\<TKey,TValue>](https://docs.microsoft.com/dotnet/api/system.collections.generic.dictionary-2) from an [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1).

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**ToDictionary\<TSource, TKey>(IEnumerable\<TSource>, Func<TSource, TKey>)**  
Creates a Dictionary\<TKey, TValue> from an IEnumerable<T> according to a specified key selector function.  
Returns a Dictionary\<TKey, TValue> that contains keys and values.  
The following code examples demonstrate how to use ToDictionary\<TSource, TKey>(IEnumerable\<TSource>, Func<TSource, TKey>) to create a Dictionary<TKey, TValue> by using a key selector.
```sql
// Dataset
DECLARE @pets = new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6}, {"Belle", 8} };

// Method 1
DECLARE @dictionary1a = @pets
                       .ToDictionary(k => k.Key, v => v.Value);

// Method 2 (Alternative usage with query syntax)
DECLARE @dictionary1b = from x in @pets
                       .ToDictionary(k => k.Key, v => v.Value)
                        select x;

@result1a =
    SELECT T.key AS petNames,
           T.value AS petAges
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@dictionary1a) AS T(key, value);

@result1b =
    SELECT T.key AS petNames,
           T.value AS petAges
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@dictionary1b) AS T(key, value);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ToDictionary/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ToDictionary/example1b.txt"
USING Outputters.Tsv();
```

**Additional Example**  
```sql
// Dataset
DECLARE @TimeZoneInfo = TimeZoneInfo.GetSystemTimeZones();

// Query
DECLARE @dictionary1c = @TimeZoneInfo.ToDictionary(x => x.Id, x => x.DisplayName);

@result1c =
    SELECT T.key AS Id,
           T.value AS DisplayName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@dictionary1c) AS T(key, value);

OUTPUT @result1c
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ToDictionary/example1c.txt"
USING Outputters.Tsv();
```

**ToDictionary\<TSource, TKey, TElement>(IEnumerable\<TSource>, Func<TSource, TKey>, Func<TSource, TElement>)**    
Creates a Dictionary\<TKey, TValue> from an IEnumerable\<T> according to specified key selector and element selector functions.     
Returns a Dictionary\<TKey, TValue> that contains values of type TElement selected from the input sequence.
```sql
// Dataset
DECLARE @pets2 = new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6}, {"Belle", 8} };

// Method 1
DECLARE @dictionary2a = @pets2
                       .ToDictionary(k => k.Key, v => v.Value > 9 ? "Old" : "Young");

// Method 2 (Alternative usage with query syntax)
DECLARE @dictionary2b = from x in @pets2
                       .ToDictionary(k => k.Key, v => v.Value > 9 ? "Old" : "Young")
                        select x;

@result2a =
    SELECT T.key AS petNames,
           T.value AS petAges
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@dictionary2a) AS T(key, value);

@result2b =
    SELECT T.key AS petNames,
           T.value AS petAges
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@dictionary2b) AS T(key, value);

OUTPUT @result2a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ToDictionary/example2a.txt"
USING Outputters.Tsv();

OUTPUT @result2b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ToDictionary/example2b.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.ToDictionary (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.todictionary)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 