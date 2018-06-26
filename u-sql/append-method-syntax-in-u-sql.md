---
title: "Append (Method Syntax in U-SQL) | Microsoft Docs"
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

# Append (Method Syntax in U-SQL) 
Appends a value to the end of the sequence.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
 

**Append\<TSource>**  
The following code example demonstrates how to use Append\<TSource>.  
```sql
@table = 
SELECT * FROM 
    ( VALUES
    ( new SQL.ARRAY<int>{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}, 
            new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14} } )
    ) AS T(numbers, pets);

DECLARE @KeyValuePair = new KeyValuePair<string, int?>("Whiskers", 6);

// Append value
@result1 =
    SELECT new SQL.ARRAY<int> (numbers.Append(10)) AS appendedNumbers
    FROM @table;

// Verify new sequence
@result1 =
    SELECT T.value AS value
    FROM @result1
    CROSS APPLY EXPLODE (appendedNumbers) AS T(value);

// Appending and verifying in one step
@result2 =
    SELECT  T.key AS key,
            T.value AS value
    FROM @table
    CROSS APPLY EXPLODE (pets.Append(@KeyValuePair)) AS T(key, value);

// Additional example
@result3 =
    SELECT T.value AS TimeZoneInfo
    FROM @table
    CROSS APPLY EXPLODE (
             TimeZoneInfo.GetSystemTimeZones()
            .Take(3)
            .Select(x => x.DisplayName)
            .Append("End of List")
            ) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Append/example1.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Append/example2.txt"
USING Outputters.Tsv();

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Append/example3.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Append (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.append)
* [Prepend (Method Syntax in U-SQL)](prepend-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)
