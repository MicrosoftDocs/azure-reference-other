---
title: "TakeWhile (Method Syntax in U-SQL) | Microsoft Docs"
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

# TakeWhile (Method Syntax in U-SQL)
Returns elements from a sequence as long as a specified condition is true, and then skips the remaining elements.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**TakeWhile\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>)**   
Returns elements from a sequence as long as a specified condition is true.   
Returns an IEnumerable\<T> that contains the elements from the input sequence starting at the first element in the linear series that does not pass the test specified by predicate.  
The following code example demonstrates how to use TakeWhile\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>) to return elements from the start of a sequence as long as a condition is true.
```sql
// Dataset
@table = 
SELECT * FROM 
    ( VALUES
    ( new SQL.ARRAY<int>{59, 73, 82, 70, 56, 92, 98, 85})
    ) AS T(grades);
 
// Queries   
@result1a =
    SELECT T.value AS usingTakeWhile
    FROM @table
    CROSS APPLY EXPLODE (grades
                        .TakeWhile(grade => grade < 80)
                        ) AS T(value);

// contrast with Where
@result1b =
    SELECT T.value AS usingWhere
    FROM @table
    CROSS APPLY EXPLODE (grades
                        .Where(grade => grade < 80)
                        .Select(x => x)
                        ) AS T(value);

// contrast with SkipWhile
@result1c =
    SELECT T.value AS usingSkipWhile
    FROM @table
    CROSS APPLY EXPLODE (grades
                        .SkipWhile(grade => grade < 80)
                        ) AS T(value);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/TakeWhile/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/TakeWhile/example1b.txt"
USING Outputters.Tsv();

OUTPUT @result1c
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/TakeWhile/example1c.txt"
USING Outputters.Tsv();
```

**TakeWhile\<TSource>(IEnumerable\<TSource>, Func<TSource, Int32, Boolean>)**   
Returns elements from a sequence as long as a specified condition is true. The element's index is used in the logic of the predicate function.  
The following code example demonstrates how to use TakeWhile\<TSource>(IEnumerable\<TSource>, Func<TSource, Int32, Boolean>) to return elements from the start of a sequence as long as a condition that uses the element's index is true.
```sql
// Dataset
DECLARE @amounts = new SQL.ARRAY<int>{5000, 2500, 9000, 8000, 6500, 4000, 1500, 5500, 9500};

// Queries
DECLARE @query2a = @amounts
                  .TakeWhile((amount, index) => index < 3);     // same as .Take(3);

DECLARE @query2b = @amounts
                  .TakeWhile((amount, index) => 
                                amount > index * 1000);         // returns while amount is greater than (amount * 1000)

// contrast with SkipWhile
DECLARE @query2c = @amounts
                  .SkipWhile((amount, index) => 
                                amount > index * 1000);         // skip while amount is greater than (amount * 1000)

@result2a =
    SELECT T.value AS usingTakeWhile
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query2a) AS T(value);

@result2b =
    SELECT T.value AS usingTakeWhile
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query2b) AS T(value);

@result2c =
    SELECT T.value AS usingSkipWhile
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query2c) AS T(value);


OUTPUT @result2a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/TakeWhile/example2a.txt"
USING Outputters.Tsv();

OUTPUT @result2b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/TakeWhile/example2b.txt"
USING Outputters.Tsv();

OUTPUT @result2c
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/TakeWhile/example2c.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.TakeWhile (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.takewhile)
* [SkipWhile (Method Syntax in U-SQL))](skipwhile-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 