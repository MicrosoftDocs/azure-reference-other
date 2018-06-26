---
title: "Distinct (Method Syntax in U-SQL) | Microsoft Docs"
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

# Distinct (Method Syntax in U-SQL)
Returns distinct elements from a sequence.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset(s) defined below.

**Distinct\<TSource>(IEnumerable\<TSource>)**  
Returns an IEnumerable\<T> that contains distinct elements from the source sequence.  
The following code example demonstrates how to use Distinct\<TSource>(IEnumerable\<TSource>) to return distinct elements from a sequence of integers.
```sql
// Dataset
@table = 
    SELECT * FROM 
    ( VALUES
    ( new SQL.ARRAY<int>{ 21, 46, 46, 55, 17, 21, 55, 55 },
        new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} })
    ) AS T(ages, petsMap);

DECLARE @KeyValuePair = new KeyValuePair<string, int?>("Boots", 14);

// Query
@result1 = 
    SELECT  T.value AS distinctAges
    FROM @table
    CROSS APPLY EXPLODE (ages.Distinct()) AS T(value);

// Alternative native method
@result1a = 
    SELECT  DISTINCT T.value AS distinctAges
    FROM @table
    CROSS APPLY EXPLODE (ages) AS T(value);

// additional example
@result2 = 
    SELECT  T.key AS distinct_pets1, 
            T.value AS distinct_pets2
    FROM @table
    CROSS APPLY EXPLODE (petsMap.Append(@KeyValuePair).Distinct()) AS T(key, value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Distinct/example1.txt"
USING Outputters.Tsv();

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Distinct/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Distinct/example2.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Distinct (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.distinct)
* [DISTINCT (U-SQL)](select-clause-u-sql.md#dist)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)