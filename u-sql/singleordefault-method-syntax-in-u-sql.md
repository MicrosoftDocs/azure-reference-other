---
title: "SingleOrDefault (Method Syntax in U-SQL) | Microsoft Docs"
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

# SingleOrDefault (Method Syntax in U-SQL)
Returns a single, specific element of a sequence, or a default value if that element is not found.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**SingleOrDefault\<TSource>(IEnumerable\<TSource>)**  
Returns the only element of a sequence, or a default value if the sequence is empty; this method throws an exception if there is more than one element in the sequence.  
The following code example demonstrates how to use SingleOrDefault\<TSource>(IEnumerable\<TSource>) to select the only element of an array.
```sql
// Dataset
@table = 
SELECT * FROM 
    ( VALUES
    (new SQL.ARRAY<int>{3}, new SQL.ARRAY<int?>{null}, new SQL.ARRAY<int>(), new SQL.ARRAY<int>{1, 2, 3, 4})
    ) AS T(col1, col2, col3, col4);

// Query
@result1 =
    SELECT 
         col1.SingleOrDefault() AS singleOrDefault,
         col2.SingleOrDefault() AS singleOrDefaultNull,
         col3.SingleOrDefault() AS singleOrDefaultEmpty           
         //, col4.SingleOrDefault() AS singleOrDefaultMultiple        // will error; InvalidOperationException
    FROM @table;

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SingleOrDefault/example1.txt"
USING Outputters.Tsv();
```


**SingleOrDefault\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>)**  
Returns the only element of a sequence that satisfies a specified condition or a default value if no such element exists; this method throws an exception if more than one element satisfies the condition.    
The following code example demonstrates how to use SingleOrDefault\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>) to select the only element of an array that satisfies a condition.
```sql
// Dataset
DECLARE @words = new SQL.ARRAY<string>{"Alpha", "Bravo", "Charlie", "Delta", "Echo"};

// Query
DECLARE @query1 = @words
                  .SingleOrDefault(x => x.Length > 10);

@result2 =
    SELECT  @query1 AS singleOrDefaultFunc,
            string.IsNullOrEmpty(@query1) ? "none" : @query1 AS singleOrDefaultFunc_newDefault
    FROM (VALUES(1)) AS A(x);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SingleOrDefault/example2.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.SingleOrDefault (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.singleordefault)
* [Single (Method Syntax in U-SQL)](single-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)