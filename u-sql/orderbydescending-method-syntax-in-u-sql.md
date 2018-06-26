---
title: "OrderByDescending (Method Syntax in U-SQL) | Microsoft Docs"
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

# OrderByDescending (Method Syntax in U-SQL)
Sorts the elements of a sequence in descending order.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**OrderByDescending\<TSource, TKey>(IEnumerable\<TSource>, Func<TSource, TKey>)**  
Sorts the elements of a sequence in descending order according to a key.   
Returns an IOrderedEnumerable\<TElement> whose elements are sorted in descending order according to a key.  
Ordered per SQL.MAP
```sql
// Dataset
@table = 
    SELECT * FROM 
    ( VALUES
    ( new SQL.MAP<string, int?>{ {"Barley", 14}, {"Belle", 13}, {"Whiskers", 6}, {"Sweetie", 2}, {"Rover", 14}, {"boots", 14} })
    ) AS T(petsMap);

// Method 1
@result1a =
    SELECT  T.key AS petName,
            T.value AS petAge
    FROM @table
    CROSS APPLY EXPLODE ( petsMap
                         .OrderByDescending(x => x.Value)
                        ) AS T(key, value);

// Method 2 (Alternative usage with query syntax)
@result1b =
    SELECT  T.key AS petName,
            T.value AS petAge
    FROM @table
    CROSS APPLY EXPLODE ( from x in petsMap
                          orderby x.Value descending
                          select x
                        ) AS T(key, value);

// Alternative native method.  See ORDER BY in OUPUT statement, below.
@result1c =
    SELECT  T.key AS petName,
            T.value AS petAge
    FROM @table
    CROSS APPLY EXPLODE (petsMap) AS T(key, value);


OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/OrderByDescending/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/OrderByDescending/example1b.txt"
USING Outputters.Tsv();

OUTPUT @result1c
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/OrderByDescending/example1c.txt"
ORDER BY petAge DESC
USING Outputters.Tsv();
```

**Additional Examples**  
```sql
// ReadOnlyCollection<TimeZoneInfo>
DECLARE @TimeZoneInfo = TimeZoneInfo.GetSystemTimeZones();

// Method 1 (Alternative usage with query syntax)
DECLARE @query2a = from x in @TimeZoneInfo
                   orderby x.BaseUtcOffset descending
                   select new SqlArray<string>{x.SupportsDaylightSavingTime.ToString(), x.BaseUtcOffset.Hours.ToString(), x.DisplayName};

// Method 2
DECLARE @query2b = @TimeZoneInfo
                  .OrderByDescending(x => x.BaseUtcOffset) 
                  .Select(x => new SqlArray<string>{x.SupportsDaylightSavingTime.ToString(), x.BaseUtcOffset.Hours.ToString(), x.DisplayName});

@result2a =
    SELECT  T.value[0] AS SupportsDaylightSavingTime,
            T.value[1] AS BaseUtcOffset,
            T.value[2] AS DisplayName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query2a) AS T(value);

@result2b =
    SELECT  T.value[0] AS SupportsDaylightSavingTime,
            T.value[1] AS BaseUtcOffset,
            T.value[2] AS DisplayName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query2b) AS T(value);

OUTPUT @result2a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/OrderByDescending/example2a.txt"
USING Outputters.Tsv();

OUTPUT @result2b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/OrderByDescending/example2b.txt"
USING Outputters.Tsv();
```


## See Also
* [Enumerable.OrderByDescending (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.orderbydescending)
* [orderby (Query Syntax in U-SQL)](orderby-clause-query-syntax-in-u-sql.md)
* [ORDER BY and OFFSET/FETCH Clause (U-SQL)](order-by-and-offset-fetch-clause-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 