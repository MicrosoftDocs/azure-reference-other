---
title: "SkipWhile (Method Syntax in U-SQL) | Microsoft Docs"
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

# SkipWhile (Method Syntax in U-SQL)
Bypasses elements in a sequence as long as a specified condition is true and then returns the remaining elements.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**SkipWhile\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>)**   
Bypasses elements in a sequence as long as a specified condition is true and then returns the remaining elements.  
Returns an IEnumerable\<T> that contains the elements from the input sequence starting at the first element in the linear series that does not pass the test specified by predicate.  
The following code example demonstrates how to use SkipWhile\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>) to skip elements of an array as long as a condition is true.
```sql
// Dataset
@table = 
SELECT * FROM 
    ( VALUES
    (new SQL.ARRAY<int>{59, 73, 82, 70, 56, 92, 98, 85})
    ) AS T(grades);

@result1 =
    SELECT T.value AS usingSkipWhile
    FROM @table
    CROSS APPLY EXPLODE (grades
                        .SkipWhile(grade => grade < 80)
                        ) AS T(value);

// contrast with Where
@result2 =
    SELECT T.value AS usingWhere
    FROM @table
    CROSS APPLY EXPLODE (grades
                        .Where(grade => grade < 80)
                        .Select(x => x)
                        ) AS T(value);

// contrast with TakeWhile
@result3 =
    SELECT T.value AS usingTakeWhile
    FROM @table
    CROSS APPLY EXPLODE (grades
                        .TakeWhile(grade => grade < 80)
                        ) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SkipWhile/example1.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SkipWhile/example2.txt"
USING Outputters.Tsv();

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SkipWhile/example3.txt"
USING Outputters.Tsv();
```

**SkipWhile\<TSource>(IEnumerable\<TSource>, Func<TSource, Int32, Boolean>)**   
Bypasses elements in a sequence as long as a specified condition is true and then returns the remaining elements. The element's index is used in the logic of the predicate function.   
The following code example demonstrates how to use SkipWhile\<TSource>(IEnumerable\<TSource>, Func<TSource, Int32, Boolean>) to skip elements of an array as long as a condition that depends on the element's index is true.
```sql
// Dataset
DECLARE @amounts = new SQL.ARRAY<int>{5000, 2500, 9000, 8000, 6500, 4000, 1500, 5500, 9500};

// Queries
DECLARE @query4 = @amounts
                  .SkipWhile((amount, index) => index < 3);     // same as .Skip(3);

DECLARE @query5 = @amounts
                  .SkipWhile((amount, index) => 
                                amount > index * 1000);         // skip while amount is greater than (amount * 1000)

// contrast with TakeWhile
DECLARE @query6 = @amounts
                  .TakeWhile((amount, index) => 
                                amount > index * 1000);         // returns while amount is greater than (amount * 1000)

@result4 =
    SELECT T.value AS usingSkipWhile
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query4) AS T(value);

@result5 =
    SELECT T.value AS usingSkipWhile
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query5) AS T(value);

@result6 =
    SELECT T.value AS usingTakeWhile
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query6) AS T(value);

OUTPUT @result4
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SkipWhile/example4.txt"
USING Outputters.Tsv();

OUTPUT @result5
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SkipWhile/example5.txt"
USING Outputters.Tsv();

OUTPUT @result6
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SkipWhile/example6.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.SkipWhile (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.skipwhile)
* [Skip (Method Syntax in U-SQL)](skip-method-syntax-in-u-sql.md)
* [Take (Method Syntax in U-SQL)](take-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)