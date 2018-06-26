---
title: "Sum (Method Syntax in U-SQL) | Microsoft Docs"
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

# Sum (Method Syntax in U-SQL)
Computes the sum of a sequence of numeric values.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The example(s) below are based on the dataset(s) defined below.  Ensure your execution includes the rowset variable(s). 

**Dataset**  
```sql
@table = 
SELECT * FROM 
    ( VALUES
    (new SQL.ARRAY<int>{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}, 
            new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} })
    ) AS T(numbers, pets);
```


**Sum(IEnumerable\<Int32>)**   
Returns the sum of the values in the sequence.
The following code example demonstrates how to use Sum(IEnumerable\<Int32>) to sum the values of a sequence.
```sql
@result1a =
    SELECT numbers.Sum() AS sum,
           pets.Values.Sum() AS sum2,
           pets.Sum(x => x.Value) AS sum3
    FROM @table;

// Alternative native method
@result1b =
    SELECT SUM(value) AS sum
    FROM @table
    CROSS APPLY EXPLODE(numbers) AS T(value);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Sum/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Sum/example1b.txt"
USING Outputters.Tsv();
```

**Sum\<TSource>(IEnumerable\<TSource>, Func<TSource, Int32>)**  
Computes the sum of the sequence of Int32 values that are obtained by invoking a transform function on each element of the input sequence.  
The following code example demonstrates how to use Sum\<TSource>(IEnumerable\<TSource>, Func<TSource, Int32>) to sum the projected values of a sequence.
```sql
@result2 =
    SELECT pets.Keys.Sum(x => x.Length) AS sum
    FROM @table;

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Sum/example2.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Sum (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.sum)
* [SUM (U-SQL)](sum-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)