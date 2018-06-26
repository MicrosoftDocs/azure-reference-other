---
title: "Max (Method Syntax in U-SQL) | Microsoft Docs"
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

# Max (Method Syntax in U-SQL)
Returns the maximum value in a sequence of values.

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
            new SQL.MAP<string, int?>{ {"Barley", 8}, {"Boots", 4}, {"Whiskers", 1} })
    ) AS T(numbers, pets);
```

**Max(IEnumerable\<Int32>)**  
Returns the maximum value in a sequence of Int32 values.  
The following code example demonstrates how to use Max(IEnumerable\<Int32>) to determine the maximum value in a sequence.
```sql
@result1 =
    SELECT numbers.Max() AS Max
    FROM @table;

// Alternative native method
@result1a =
    SELECT MAX(T.value) AS Max
    FROM @table
    CROSS APPLY EXPLODE (numbers) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Max/example1.txt"
USING Outputters.Tsv();

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Max/example1a.txt"
USING Outputters.Tsv();
```

**Max\<TSource>(IEnumerable\<TSource>, Func<TSource, Int32>)**   
Invokes a transform function on each element of a sequence and returns the maximum Int32 value.  
The following code example demonstrates how to use Max\<TSource>(IEnumerable\<TSource>, Func<TSource, Int32>) to determine the maximum value in a sequence of projected values.
```sql
@result2 =
    SELECT pets.Max(x => x.Value + x.Key.Length) AS Max_AgePlusNameLength
    FROM @table;

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Max/example2.txt"
USING Outputters.Tsv();
```


## See Also
* [Enumerable.Max (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.max)
* [MAX (U-SQL)](max-u-sql.md)
* [Min (Method Syntax in U-SQL)](min-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)