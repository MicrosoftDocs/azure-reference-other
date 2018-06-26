---
title: "Reverse (Method Syntax in U-SQL) | Microsoft Docs"
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

# Reverse (Method Syntax in U-SQL)
Inverts the order of the elements in a sequence.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**Reverse\<TSource>(IEnumerable\<TSource>)**  
The following code example demonstrates how to use Reverse<TSource> to reverse the order of elements in an array and a map.
```sql
// Dataset
@table = 
    SELECT * FROM 
        ( VALUES
        (new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"},
                    new SQL.MAP<string, int?>{ {"Alpha", 1}, {"Bravo", 2}, {"Charlie", 3}, {"Delta", 4} })
        ) AS T(array, map);

// Queries
@result1 =
    SELECT T.value AS reversedValues
    FROM @table
    CROSS APPLY EXPLODE (array.Reverse()) AS T(value);

@result2 =
    SELECT T.key AS reversedKeys,
           T.value AS reversedValues
    FROM @table
    CROSS APPLY EXPLODE (map.Reverse()) AS T(key, value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Reverse/example1.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Reverse/example2.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Reverse (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.reverse)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)