---
title: "ElementAtOrDefault (Method Syntax in U-SQL) | Microsoft Docs"
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

# ElementAtOrDefault (Method Syntax in U-SQL)
Returns the element at a specified index in a sequence or a default value if the index is out of range.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**ElementAtOrDefault\<TSource>(IEnumerable\<TSource>, Int32)**  
The following code example demonstrates how to use ElementAtOrDefault\<TSource>. 
This example uses an index that is outside the bounds of the array.
```sql
// Dataset
@table = 
SELECT * FROM 
    ( VALUES
    (new SQL.ARRAY<int>{1, 2, 3, 4, 5, 6, 7, 8, 9, 0}, 
            new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"})
    ) AS T(numbers, words);

@result1 =
    SELECT  numbers.ElementAtOrDefault(0) AS ElementAtOrDefault_int,
            numbers.ElementAtOrDefault(20) AS ElementAtOrDefault_int_outOfBounds,
            words.ElementAtOrDefault(0) AS ElementAtOrDefault_string,
            words.ElementAtOrDefault(20) AS ElementAtOrDefault_string_outOfBounds
    FROM @table;

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ElementAtOrDefault/example1.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.ElementAtOrDefault (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.elementatordefault)
* [Enumerable.ElementAt (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.elementat)
* [ElementAt (Method Syntax in U-SQL)](elementat-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)  