---
title: "Average (Method Syntax in U-SQL) | Microsoft Docs"
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

# Average (Method Syntax in U-SQL)
Computes the average of a sequence of numeric values.

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
            new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"})
    ) AS T(numbers, words);

DECLARE @numbers = new SQL.ARRAY<int>{0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
```

**Average(IEnumerable\<Int32>)**  
Computes the average of a sequence of Int32 values.  
The following code example demonstrates how to use Average(IEnumerable\<Int32>) to calculate an average.
```sql
@result1 =
    SELECT 
        numbers.Average() AS AverageOfValues,
        @numbers.Average() AS Average2,
        numbers.Sum() / (double)numbers.Count AS Average3
    FROM @table;

// Alternative native method
@result1a =
    SELECT 
        AVG(T.value) AS AverageOfValues
    FROM @table
    CROSS APPLY EXPLODE (numbers) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Average/example1.txt"
USING Outputters.Tsv();

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Average/example1a.txt"
USING Outputters.Tsv();
```

**Average\<TSource>(IEnumerable\<TSource>, Func<TSource, Int32>)**  
Computes the average of a sequence of Int32 values that are obtained by invoking a transform function on each element of the input sequence.  
The following code example demonstrates how to use Average\<TSource>(IEnumerable<TSource>, Func<TSource, Int32>) to calculate an average.
```sql
@result2 =
    SELECT 
        words.Average(x => x.Length) AS AverageWordLength
    FROM @table;

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Average/example2.txt"
USING Outputters.Tsv();
```

**Average with Nested Values**  
```sql
// Dataset
DECLARE @person = 
    new SQL.MAP<string, SQL.MAP<string, int?>>{
                {"Haas", new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} } }
             };

// Method 1
DECLARE @complex1 = @person
                    .SelectMany(v => v.Value)
                    .Average(k => k.Value);

// Method 2
DECLARE @complex2 = (from x in @person
                    .SelectMany(v => v.Value)
                    select x.Value).Average();

@resultC1 =
    SELECT @complex1 AS Average_petAge1,
           @complex2 AS Average_petAge2
    FROM (VALUES(1)) AS A(x);

OUTPUT @resultC1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Average/complex1.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Average (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.average)
* [AVG (U-SQL)](avg-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)
