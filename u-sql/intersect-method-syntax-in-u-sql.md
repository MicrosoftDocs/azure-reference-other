---
title: "Intersect (Method Syntax in U-SQL) | Microsoft Docs"
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

# Intersect (Method Syntax in U-SQL)
Produces the set intersection of two sequences.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Intersect\<TSource>(IEnumerable\<TSource>, IEnumerable\<TSource>)**  
Returns a sequence that contains the elements that form the set intersection of two sequences.  
The following code example demonstrates how to use Intersect\<TSource>(IEnumerable\<TSource>, IEnumerable\<TSource>) to return the elements that appear in each of two sequences of integers.
```sql
// Dataset
@table1 = 
SELECT * FROM 
    ( VALUES
    (1, new SQL.ARRAY<int>{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}, 
            new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} })
    ) AS T(id, numbers, pets);

@table2 = 
SELECT * FROM 
    ( VALUES
    (1, new SQL.ARRAY<int>{1, 3, 5, 7, 9}, 
            new SQL.MAP<string, int?>{ {"Boots", 14}, {"Daisy", 4} })
    ) AS T(id, numbers, pets);

DECLARE @someNumbers1 = new SQL.ARRAY<int>{1, 3, 5, 7, 9};
DECLARE @someNumbers2 = new SQL.ARRAY<int>{2, 3, 4, 5, 6};

// Queries
@result1 =
    SELECT  T.value AS Intersect
    FROM @table1
    CROSS APPLY EXPLODE (@someNumbers1.Intersect(@someNumbers2)) AS T(value);

@result2 =
    SELECT  T.value AS Intersect
    FROM @table2
    CROSS APPLY EXPLODE (numbers.Intersect(@someNumbers2)) AS T(value);

@result3 =
    SELECT  T.key AS exceptKey,
            T.value AS exceptValue
    FROM @table1 AS a
    JOIN @table2 AS b
    ON a.id == b.id
    CROSS APPLY EXPLODE (a.pets.Intersect(b.pets)) AS T(key, value);

// Alternative native method
@result3a =
    SELECT  T.key AS a, T.value AS b FROM @table1 CROSS APPLY EXPLODE (pets) AS T(key, value)
    INTERSECT
    SELECT  T.key AS a, T.value AS b FROM @table2 CROSS APPLY EXPLODE (pets) AS T(key, value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Intersect/example1.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Intersect/example2.txt"
USING Outputters.Tsv();

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Intersect/example3.txt"
USING Outputters.Tsv();

OUTPUT @result3a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Intersect/example3a.txt"
USING Outputters.Tsv();
```
 
 
## See Also
* [Enumerable.Intersect (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.intersect)
* [INTERSECT Expression (U-SQL)](intersect-expression-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)