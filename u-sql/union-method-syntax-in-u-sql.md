---
title: "Union (Method Syntax in U-SQL) | Microsoft Docs"
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

# Union (Method Syntax in U-SQL)
Produces the set union of two sequences.

> [!NOTE]  
> LINQ Union is similiar to [U-SQL UNION](union-and-outer-union-expression-u-sql.md)  
> [LINQ Concat](concat-method-syntax-in-u-sql.md) is similiar to [U-SQL UNION ALL](union-and-outer-union-expression-u-sql.md)  

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**Union\<TSource>(IEnumerable\<TSource>, IEnumerable\<TSource>)**   
Produces the set union of two sequences by using the default equality comparer.   
Returns an IEnumerable\<T> that contains the elements from both input sequences, excluding duplicates.   
The following code example demonstrates how to use Union\<TSource>(IEnumerable\<TSource>, IEnumerable\<TSource>) to obtain the union of two sequences.
```sql
// Datasets
@table = 
    SELECT * FROM 
        ( VALUES
        (new SQL.ARRAY<string>{"Barley", "Boots", "Whiskers"},
            new SQL.ARRAY<string>{"Snoopy", "Fido", "Barley"})
        ) AS T(cats, dogs);

DECLARE @cats = new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} };
DECLARE @dogs = new SQL.MAP<string, int?>{ {"Snoopy", 14}, {"Fido", 9}, {"Barley", 10} };


// Method 1
DECLARE @union1a = @cats.Keys
                  .Union
                  (@dogs.Keys);

// Method 2 (Alternative usage with query syntax)
DECLARE @union1b = from x in @cats.Keys
                  .Union
                  (@dogs.Keys)
                   select x;

// Contrast with Concat
DECLARE @concat1 = @cats.Keys
                  .Concat
                  (@dogs.Keys);

@result1a =
    SELECT T.value AS value
    FROM @table
    CROSS APPLY EXPLODE (@union1a) AS T(value);

@result1b =
    SELECT T.value AS value
    FROM @table
    CROSS APPLY EXPLODE (@union1b) AS T(value);

@result2 =
    SELECT T.value AS value
    FROM @table
    CROSS APPLY EXPLODE (@concat1) AS T(value);


// additional example
@result3 =
    SELECT T.value AS value
    FROM @table 
    CROSS APPLY EXPLODE (cats.Union(dogs)) AS T(value);

// Alternative native method
@result4 =
    SELECT T.value AS value FROM @table CROSS APPLY EXPLODE (cats) AS T(value)
    UNION 
    SELECT T.value AS value FROM @table CROSS APPLY EXPLODE (dogs) AS T(value);


OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Union/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Union/example1b.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Union/example2.txt"
USING Outputters.Tsv();

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Union/example3.txt"
USING Outputters.Tsv();

OUTPUT @result4
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Union/example4.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Union (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.union)
* [UNION and OUTER UNION Expression (U-SQL)](union-and-outer-union-expression-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)