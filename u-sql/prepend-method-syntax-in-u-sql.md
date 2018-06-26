---
title: "Prepend (Method Syntax in U-SQL) | Microsoft Docs"
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

# Prepend (Method Syntax in U-SQL)
Adds a value to the beginning of the sequence.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**Prepend\<TSource>(IEnumerable\<TSource>, TSource)**  
The following code example demonstrates how to use Prepend\<TSource>. 
```sql
@table = 
SELECT * FROM 
    ( VALUES
    ( new SQL.ARRAY<int>{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}, 
            new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14} } )
    ) AS T(numbers, pets);

DECLARE @KeyValuePair = new KeyValuePair<string, int?>("Whiskers", 6);

// Prepend value
@result1 =
    SELECT new SQL.ARRAY<int> (numbers.Prepend(10)) AS prependedNumbers
    FROM @table;

// Verify new sequence
@result1 =
    SELECT T.value AS value
    FROM @result1
    CROSS APPLY EXPLODE (prependedNumbers) AS T(value);


// Prepending and verifying in one step
@result2 =
    SELECT  T.key AS key,
            T.value AS value
    FROM @table
    CROSS APPLY EXPLODE (pets.Prepend(@KeyValuePair)) AS T(key, value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Prepend/example1.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Prepend/example2.txt"
USING Outputters.Tsv();
```

**Additional example**  
```sql
@result3 =
    SELECT 
    T.value AS timeZoneInfo
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (
                 TimeZoneInfo.GetSystemTimeZones()
                .Take(3)
                .Select(x => x.DisplayName)
                .Prepend("Start of List")
                ) AS T(value);

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Prepend/example3.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Prepend (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.prepend)
* [Append (Method Syntax in U-SQL)](append-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)