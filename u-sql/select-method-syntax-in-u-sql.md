---
title: "Select (Method Syntax in U-SQL) | Microsoft Docs"
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

# Select (Method Syntax in U-SQL)
Projects each element of a sequence into a new form.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**Select\<TSource, TResult>(IEnumerable\<TSource>, Func<TSource, TResult>)**  
Projects each element of a sequence into a new form.   
The following code example demonstrates how to use Select\<TSource, TResult>(IEnumerable\<TSource>, Func<TSource, TResult>) to project over a sequence of values.
```sql
// Dataset
DECLARE @TimeZoneInfo = TimeZoneInfo.GetSystemTimeZones(); 

// Queries
// Method 1
DECLARE @query1a = @TimeZoneInfo
                  .Select(x => x.DisplayName);

// Method 2 (Query Syntax)
DECLARE @query1b = from x in @TimeZoneInfo
                   select x.DisplayName;

@result1a =
    SELECT T.value AS DisplayName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1a) AS T(value);

@result1b =
    SELECT T.value AS DisplayName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1b) AS T(value);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Select/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Select/example1b.txt"
USING Outputters.Tsv();
```

**Additional basic examples**  
```sql
// Dataset
DECLARE @map = new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} };

// Method 1
DECLARE @query1c = @map
                  .Select(x => x.Key);

// Method 2 (Query Syntax)
DECLARE @query1d = from x in @map
                   select x.Key;

@result1c =
    SELECT T.value AS petNames
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1c) AS T(value);

@result1d =
    SELECT T.value AS petNames
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1d) AS T(value);

OUTPUT @result1c
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Select/example1c.txt"
USING Outputters.Tsv();

OUTPUT @result1d
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Select/example1d.txt"
USING Outputters.Tsv();
```

**Select mutiple values**  
```sql
// Dataset
DECLARE @TimeZoneInfo2 = TimeZoneInfo.GetSystemTimeZones(); 

// Method 1
DECLARE @query2a = @TimeZoneInfo2
                  .Select(x => new SQL.ARRAY<string>{x.Id, x.DisplayName});

// Method 2 (Query Syntax)
DECLARE @query2b = from x in @TimeZoneInfo2
                   select new SQL.ARRAY<string>{x.Id, x.DisplayName};

@result2a =
    SELECT  T.value[0] AS Id,
            T.value[1] AS DisplayName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query2a) AS T(value);

@result2b =
    SELECT  T.value[0] AS Id,
            T.value[1] AS DisplayName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query2b) AS T(value);

OUTPUT @result2a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Select/example2a.txt"
USING Outputters.Tsv();

OUTPUT @result2b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Select/example2b.txt"
USING Outputters.Tsv();
```

**Transform values**  
```sql
// Dataset
DECLARE @numbers = new SQL.ARRAY<int>{0, 5, 10};

// Method 1
DECLARE @query3a = @numbers
                  .Select(x => new SQL.ARRAY<int>{x, x+2, x*2});

// Method 2 (Query Syntax)
DECLARE @query3b = from x in @numbers
                   select new SQL.ARRAY<int>{x, x+2, x*2};

@result3a =
    SELECT  T.value[0] AS number,
            T.value[1] AS plusTwo,
            T.value[2] AS timesTwo
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query3a) AS T(value);

@result3b =
    SELECT  T.value[0] AS number,
            T.value[1] AS plusTwo,
            T.value[2] AS timesTwo
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query3b) AS T(value);

OUTPUT @result3a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Select/example3a.txt"
USING Outputters.Tsv();

OUTPUT @result3b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Select/example3b.txt"
USING Outputters.Tsv();
```

**Select\<TSource, TResult>(IEnumerable\<TSource>, Func<TSource, Int32, TResult>)**  
Projects each element of a sequence into a new form by incorporating the element's index.  
The following code example demonstrates how to use Select\<TSource, TResult>(IEnumerable\<TSource>, Func<TSource, Int32, TResult>) to project over a sequence of values and use the index of each element.
```sql
// Dataset
DECLARE @words = new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"};

// Query
DECLARE @query4 = @words
                 .Select( (word, index) => new KeyValuePair<int, string>(index, word) );

@result4 =
    SELECT  T.key AS index,
            T.value AS word
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query4) AS T(key, value);

OUTPUT @result4
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Select/example4.txt"
USING Outputters.Tsv();
```


## See Also
* [Enumerable.Select (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.select)
* [select (Query Syntax in U-SQL)](select-clause-query-syntax-in-u-sql.md)
* [SELECT Clause (U-SQL)](select-clause-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 