---
title: "SelectMany (Method Syntax in U-SQL) | Microsoft Docs"
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

# SelectMany (Method Syntax in U-SQL)
Projects each element of a sequence to an [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1) and flattens the resulting sequences into one sequence.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- Some of the examples below are based on the dataset(s) defined below. 

**Dataset**   
```sql
// Nested maps
DECLARE @people = 
    new SQL.MAP<string, SQL.MAP<string, int?>>{
                {"Haas", new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} } },
                {"Fakhouri", new SQL.MAP<string, int?>{ {"Snowball", 1} } },
                {"Antebi", new SQL.MAP<string, int?>{ {"Belle", 8} } },
                {"Philips", new SQL.MAP<string, int?>{ {"Sweetie", 2}, {"Rover", 13} } },
                {"James", new SQL.MAP<string, int?>() }
            };
```

**Return nested maps**  
```sql
// Method 1
DECLARE @query1a = @people
                  .SelectMany(v => v.Value);
                   
/* Method 1 Alternative
DECLARE @query1a = @people.Values
                  .SelectMany(x => x);
*/


// Method 2
DECLARE @query1b = from x in @people
                  .SelectMany(v => v.Value)
                   select x;

/* Method 2 Alternative
DECLARE @query1b = from x in @people.Values
                  .SelectMany(v => v)
                   select x;  
*/


// Query Syntax
DECLARE @query1c = from x in @people
                   from a in x.Value
                   select a;

// Alternative native method
@result1d =
    SELECT  T.Key AS key, 
            T.Value AS value
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@people) AS S(Key, Value)
    CROSS APPLY EXPLODE (Value) AS T(Key, Value);


@result1a =
    SELECT  T.a AS key, 
            T.b AS value
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1a) AS T(a, b);

@result1b =
    SELECT  T.Key AS key, 
            T.Value AS value
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1b) AS T(Key, Value);

@result1c =
    SELECT  T.Key AS key, 
            T.Value AS value
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1c) AS T(Key, Value);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SelectMany/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SelectMany/example1b.txt"
USING Outputters.Tsv();

OUTPUT @result1c
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SelectMany/example1c.txt"
USING Outputters.Tsv();

OUTPUT @result1d
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SelectMany/example1d.txt"
USING Outputters.Tsv();
```

**Using SelectMany to return a nested map.Key**  
```sql
// Method 1
DECLARE @query2a = @people
                    .SelectMany(v => v.Value)
                    .Select(k => k.Key);

// Method 2
DECLARE @query2b = from x in @people
                   .SelectMany(v => v.Value)
                   select x.Key;

@result2a =
    SELECT  T.Key AS key
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query2a) AS T(Key);

@result2b =
    SELECT  T.Key AS key
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query2b) AS T(Key);

OUTPUT @result2a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SelectMany/example2a.txt"
USING Outputters.Tsv();

OUTPUT @result2b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SelectMany/example2b.txt"
USING Outputters.Tsv();
```

**Cartesian product (cross-join)**  
```sql
// Dataset
DECLARE @pets1 = new SQL.ARRAY<string>{"Scruffy", "Sam", "Walker"};
DECLARE @pets2 = new SQL.ARRAY<string>{"Scratches", "Diesel", "Sugar"};

                            
// Method 1
DECLARE @query3a = from a in @pets1
                   from b in @pets2
                   select new SQL.ARRAY<string>{a, b};

// Method 2
DECLARE @query3b = @pets1
                  .SelectMany(a => @pets2,
                                (a, b) => new SQL.ARRAY<string>{a, b});

@result3a =
    SELECT  T.value[0] AS crossPets1,
            T.value[1] AS crossPets2
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query3a) AS T(value);

@result3b =
    SELECT  T.value[0] AS crossPets1,
            T.value[1] AS crossPets2
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query3b) AS T(value);

OUTPUT @result3a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SelectMany/example3a.txt"
USING Outputters.Tsv();

OUTPUT @result3b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SelectMany/example3b.txt"
USING Outputters.Tsv();
```

**Compare the output between `Select` and `SelectMany`**  
```sql
// Dataset
DECLARE @query4a = @pets1.SelectMany(x => x);
DECLARE @query4b = @pets1.Select(x => x);

@result4a =
    SELECT T.value.ToString() AS words_SelectMany
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query4a) AS T(value);

@result4b =
    SELECT T.value AS words_Select
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query4b) AS T(value);

OUTPUT @result4a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SelectMany/example4a.txt"
USING Outputters.Tsv();

OUTPUT @result4b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SelectMany/example4b.txt"
USING Outputters.Tsv();
```


## See Also
* [Enumerable.SelectMany (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.selectmany)
* [Select (Method Syntax in U-SQL)](select-method-syntax-in-u-sql.md)
* [select (Query Syntax in U-SQL)](select-clause-query-syntax-in-u-sql.md)
* [SELECT Clause (U-SQL)](select-clause-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 