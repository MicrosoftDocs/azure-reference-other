---
title: "Aggregate (Method Syntax in U-SQL) | Microsoft Docs"
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

# Aggregate (Method Syntax in U-SQL)
Applies an accumulator function over a sequence.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset(s) defined below. 
 
**Dataset**   
```sql
@table = 
SELECT * FROM 
    ( VALUES
    (new SQL.ARRAY<int>{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}, 
        new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"},
            "Haas", new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} })
    ) AS T(numbers, words, lastName, pets);

DECLARE @pets = new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} };
```

**Aggregate\<TSource>**  
Applies an accumulator function over a sequence.  Returns the final accumulator value.
Elements in the sequence are aggregated into a single value.
```sql
DECLARE @query1 = @pets.Keys
                  .Aggregate((x, y) => x + "," + y);

@result1 =
    SELECT words.Aggregate((x, y) => x + "," + y) AS Aggregate_strings1,
           words.Aggregate((accumulator , nextValue) => accumulator  + "," + nextValue) AS Aggregate_strings2,
           numbers.Aggregate((x, y) => x + y) AS Aggregate_numbers,
           lastName + ": " + @query1 AS Aggregate_mapKeys1,
           lastName + ": " + pets.Select(k => k.Key).Aggregate((x, y) => x + "," + y) AS Aggregate_mapKeys2
    FROM @table;

// Alternative method
@result1a =
    SELECT string.Join(",", words) AS Join_strings,
           lastName + ": " + string.Join(",", pets.Keys) AS Join_mapKeys,
           numbers.Sum() AS Sum_numbers
    FROM @table;

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Aggregate/example1.txt"
USING Outputters.Tsv();

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Aggregate/example1a.txt"
USING Outputters.Tsv();
```

**Aggregate<TSource, TAccumulate>**  
Applies an accumulator function over a sequence. The specified seed value is used as the initial accumulator value.  
Returns the final accumulator value.
The following code example demonstrates how to use Aggregate<TSource, TAccumulate> to apply an accumulator function and use a seed value.
```sql
@result2 =
    SELECT 
        words.Aggregate("Foxtrot", (x, y) => x + "," + y) AS aggregateSeed_strings1,
        numbers.Aggregate(10, (x, y) => x + y) AS aggregateSeed_numbers,

        // Compare w_seed and wo_seed and note difference when a seed value is not used.
        numbers.Aggregate(0, (total, next) =>
                                        next % 2 == 0 ? total + 1 : total) AS w_seed,
        numbers.Aggregate((total, next) =>
                                        next % 2 == 0 ? total + 1 : total) AS wo_seed,

        // To avoid possible aggregate issues as seen above, use standard query operators such as Count.
        numbers.Where(x => x % 2 == 0).Count() AS count_evenNumbers,

        // Identify longest element, including the seed value "Apple", in the sequence.
        words.Aggregate("Apple",
                        (longest, next) =>
                        next.Length > longest.Length ? next : longest) AS longestWord,

        // Using lastName as the seed value
        pets
        .Select(k => k.Key)
        .Aggregate(lastName + "(owner)", (x, y) => x + "," + y) AS aggregateSeed_strings2
    FROM @table;

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Aggregate/example2.txt"
USING Outputters.Tsv();
```

**Aggregate<TSource, TAccumulate, TResult>**  
Applies an accumulator function over a sequence. The specified seed value is used as the initial accumulator value, and the specified function is used to select the result value.
Returns the transformed final accumulator value.  
The following code example demonstrates how to use Aggregate<TSource, TAccumulate, TResult> to apply an accumulator function and a result selector.
```sql
@result3 =
    SELECT 
        // Identify longest element, including the seed value "Apple", in the sequence.
        words.Aggregate("Apple",
                        (longest, next) =>
                            next.Length > longest.Length ? next : longest,
                            // Return the final result as an upper case string.
                            z => z.ToUpper()) AS longestWord_upperCase
    FROM @table;

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Aggregate/example3.txt"
USING Outputters.Tsv();
```

**Aggregate and Nested Values**
```sql
// Dataset
@tableC = 
    SELECT * FROM 
    ( VALUES
    (new SQL.MAP<string, SQL.MAP<string, int?>>{
                {"Haas", new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} } }
            })
    ) AS T(col1);

DECLARE @person = 
    new SQL.MAP<string, SQL.MAP<string, int?>>{
                {"Haas", new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} } }
            };

// Query
DECLARE @complex1 = @person
                    .SelectMany(v => v.Value)
                    .Select(k => k.Value)
                    .Aggregate((x, y) => x + y);

// Alternative method
DECLARE @complex2 = (from x in @person
                     .SelectMany(v => v.Value)              
                     select x.Value)
                     .Aggregate((x, y) => x + y);


@resultC1 =
    SELECT  @complex1 AS Aggregate_nestedNumbersVariable1,
            @complex2 AS Aggregate_nestedNumbersVariable2,
            col1.SelectMany(v => v.Value).Select(k => k.Value).Aggregate((x, y) => x + y) AS Aggregate_nestedValueColumn,
            col1.SelectMany(v => v.Value).Select(k => k.Key).Aggregate((x, y) => x + "," + y) AS Aggregate_nestedKeyColumn
    FROM @tableC;

OUTPUT @resultC1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Aggregate/complex1.txt"
USING Outputters.Tsv();
```


## See Also
* [Enumerable.Aggregate (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.aggregate)
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)
