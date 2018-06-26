---
title: "ThenBy (Method Syntax in U-SQL) | Microsoft Docs"
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

# ThenBy (Method Syntax in U-SQL)
Performs a subsequent ordering of the elements in a sequence in ascending order.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**ThenBy\<TSource, TKey>(IOrderedEnumerable\<TSource>, Func<TSource, TKey>)**  
Performs a subsequent ordering of the elements in a sequence in ascending order according to a key.  
Returns an IOrderedEnumerable\<TElement> whose elements are sorted according to a key.  
The following code example demonstrates how to use ThenBy\<TSource, TKey>(IOrderedEnumerable\<TSource>, Func<TSource, TKey>) to perform a secondary ordering of the elements in a sequence.
```sql
// Dataset
@table = 
    SELECT * FROM 
    ( VALUES
    ( new SQL.MAP<string, int?>{ {"Barley", 14}, {"Belle", 13}, {"Whiskers", 6}, {"Sweetie", 2}, {"Rover", 14}, {"boots", 14} })
    ) AS T(petsMap);

// Queries
// Method 1
@result1 =
    SELECT  T.key AS petName,
            T.value AS petAge
    FROM @table
    CROSS APPLY EXPLODE (petsMap
                        .OrderBy(x => x.Value)
                        .ThenBy(x => x.Key)
                        ) AS T(key, value);

// Method 2a (Query Syntax)
@result2a =
    SELECT  T.key AS petName,
            T.value AS petAge
    FROM @table
    CROSS APPLY EXPLODE (from x in petsMap
                         orderby x.Value, x.Key
                         select x
                        ) AS T(key, value);

// Method 2b (Query & Method Syntax)
@result2b =
    SELECT  T.key AS petName,
            T.value AS petAge
    FROM @table
    CROSS APPLY EXPLODE ( (from x in petsMap
                           orderby x.Value
                           select x)
                          .ThenBy(x => x.Key)
                        ) AS T(key, value);

// Alternative native method.  See ORDER BY in OUPUT statement, below.
@result3 =
    SELECT  T.key AS petName,
            T.value AS petAge
    FROM @table
    CROSS APPLY EXPLODE (petsMap) AS T(key, value);


OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ThenBy/example1.txt"
USING Outputters.Tsv();

OUTPUT @result2a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ThenBy/example2a.txt"
USING Outputters.Tsv();

OUTPUT @result2b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ThenBy/example2b.txt"
USING Outputters.Tsv();

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ThenBy/example3.txt"
ORDER BY petAge, petName
USING Outputters.Tsv();
```

**Additional Examples**  
```sql
// Dataset
// ReadOnlyCollection<TimeZoneInfo>
DECLARE @TimeZoneInfo = TimeZoneInfo.GetSystemTimeZones();

// Queries
// Method 1 (Query Syntax)
DECLARE @query4a = from x in @TimeZoneInfo
                   orderby x.SupportsDaylightSavingTime, x.BaseUtcOffset
                   select new SqlArray<string>{x.SupportsDaylightSavingTime.ToString(), x.BaseUtcOffset.Hours.ToString(), x.DisplayName};

// Method 2
DECLARE @query4b = @TimeZoneInfo
                   .OrderBy(x => x.SupportsDaylightSavingTime) 
                   .ThenBy(x => x.BaseUtcOffset)
                   .Select(x => new SqlArray<string>{x.SupportsDaylightSavingTime.ToString(), x.BaseUtcOffset.Hours.ToString(), x.DisplayName});

@result4a =
    SELECT  T.value[0] AS SupportsDaylightSavingTime,
            T.value[1] AS BaseUtcOffset,
            T.value[2] AS DisplayName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query4a) AS T(value);

@result4b =
    SELECT  T.value[0] AS SupportsDaylightSavingTime,
            T.value[1] AS BaseUtcOffset,
            T.value[2] AS DisplayName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query4b) AS T(value);

OUTPUT @result4a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ThenBy/example4a.txt"
USING Outputters.Tsv();

OUTPUT @result4b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ThenBy/example4b.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.ThenBy (System.Linq)](https://docs.microsoft.com//dotnet/api/system.linq.enumerable.thenby)
* [OrderBy (Method Syntax in U-SQL)](orderby-method-syntax-in-u-sql.md)
* [orderby (Query Syntax in U-SQL)](orderby-clause-query-syntax-in-u-sql.md)
* [ORDER BY and OFFSET/FETCH Clause (U-SQL)](order-by-and-offset-fetch-clause-u-sql.md)
* [ThenByDescending (Method Syntax in U-SQL)](thenbydescending-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 