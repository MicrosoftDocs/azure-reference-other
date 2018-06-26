---
title: "Where (Method Syntax in U-SQL) | Microsoft Docs"
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

# Where (Method Syntax in U-SQL)
Filters a sequence of values based on a predicate.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The example(s) below are based on the dataset(s) defined below.  Ensure your execution includes the rowset variable(s).  

**Dataset**    
```sql
DECLARE @numbers = new SQL.ARRAY<int>{ 0, 30, 20, 15, 90, 85, 40, 75 };
```

**Where\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>)**    
Filters a sequence of values based on a predicate.   
Returns an IEnumerable\<T> that contains elements from the input sequence that satisfy the condition.   
The following code example demonstrates how to use Where\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>) to filter a sequence.
```sql
// Method 1
DECLARE @query1a = @numbers
                  .Where(x => x > 50);

// Method 2 (Alternative usage with query syntax)
DECLARE @query1b = from x in @numbers
                   where x > 50
                   select x;


// Alternative native method
@result2 =
    SELECT T.value AS petNames
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@numbers) AS T(value)
    WHERE T.value > 50;

@result1a =
    SELECT T.value AS petNames
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1a) AS T(value);

@result1b =
    SELECT T.value AS petNames
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1b) AS T(value);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Where/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Where/example1b.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Where/example2.txt"
USING Outputters.Tsv();
```


**Where\<TSource>(IEnumerable\<TSource>, Func<TSource, Int32, Boolean>)**    
Filters a sequence of values based on a predicate. Each element's index is used in the logic of the predicate function.   
The following code example demonstrates how to use Where\<TSource>(IEnumerable\<TSource>, Func<TSource, Int32, Boolean>) to filter a sequence based on a predicate that involves the index of each element.
```sql
// Method 1
DECLARE @query3a = @numbers
                  .Where((number, index) => number <= index * 10);

// Method 2 (Alternative usage with query syntax)
DECLARE @query3b = from x in @numbers
                  .Select((number, index) => new {number, index})
                   where (x.number <= x.index * 10)
                   select x.number;

@result3a =
    SELECT T.value AS petNames
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query3a) AS T(value);

@result3b =
    SELECT T.value AS petNames
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query3b) AS T(value);

OUTPUT @result3a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Where/example3a.txt"
USING Outputters.Tsv();

OUTPUT @result3b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Where/example3b.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.where (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.where)
* [where clause (Query Syntax in U-SQL)](where-clause-query-syntax-in-u-sql.md)
* [WHERE Clause (U-SQL)](where-clause-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)