---
title: "Except (Method Syntax in U-SQL) | Microsoft Docs"
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

# Except (Method Syntax in U-SQL)
Produces the set difference of two sequences.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset(s) defined below.
 
**Dataset**  
```sql
@table = 
SELECT * FROM 
    ( VALUES
    (1, new SQL.ARRAY<int>{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}, 
            new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} })
    ) AS T(id, numbers, pets);

@table2 = 
SELECT * FROM 
    ( VALUES
    (1, new SQL.ARRAY<int>{1, 3, 5, 7, 9}, 
            new SQL.MAP<string, int?>{ {"Boots", 14} })
    ) AS T(id, numbers, pets);

DECLARE @someNumbers = new SQL.ARRAY<int>{1, 3, 5, 7, 9};
```

**Except\<TSource>(IEnumerable\<TSource>, IEnumerable\<TSource>) - Basic Example**  
Returns a sequence that contains the set difference of the elements of two sequences.  
The following code example demonstrates how to use the Except\<TSource>(IEnumerable\<TSource>, IEnumerable\<TSource>) method to compare two sequences of numbers and return elements that appear only in the first sequence.
```sql
@result1 =
    SELECT  T.value AS Except
    FROM  @table
    CROSS APPLY EXPLODE (numbers.Except(@someNumbers)) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Except/example1.txt"
USING Outputters.Tsv();
```

**Except\<TSource>(IEnumerable\<TSource>, IEnumerable\<TSource>) - Additional Example**  
```sql
@result2 =
    SELECT  T.key AS exceptKey,
            T.value AS exceptValue
    FROM @table AS a
    JOIN @table2 AS b
    ON a.id == b.id
    CROSS APPLY EXPLODE (a.pets.Except(b.pets)) AS T(key, value);

// Alternative native method.
@result2a =
    SELECT  T.key AS a, T.value AS b FROM @table CROSS APPLY EXPLODE (pets) AS T(key, value)
    EXCEPT
    SELECT  T.key AS a, T.value AS b FROM @table2 CROSS APPLY EXPLODE (pets) AS T(key, value);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Except/example2.txt"
USING Outputters.Tsv();

OUTPUT @result2a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Except/example2a.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Except (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.except)
* [EXCEPT Expression (U-SQL)](except-expression-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)