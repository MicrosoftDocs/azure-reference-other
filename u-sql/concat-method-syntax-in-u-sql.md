---
title: "Concat (Method Syntax in U-SQL) | Microsoft Docs"
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

# Concat (Method Syntax in U-SQL)
Concatenates two sequences.

> [!NOTE]  
> LINQ Concat is similiar to [U-SQL UNION ALL](union-and-outer-union-expression-u-sql.md)  
> [LINQ Union](union-method-syntax-in-u-sql.md) is similiar to [U-SQL UNION](union-and-outer-union-expression-u-sql.md)

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Concat\<TSource>**   
The following code examples demonstrate how to use Concat\<TSource>(IEnumerable\<TSource>, IEnumerable\<TSource>) to concatenate two sequences.
```sql
// Concat entire SQL.MAP
DECLARE @Concat1 = @cats
                   .Concat
                   (@dogs);

// Concat SQL.MAP Keys
// Method 1a
DECLARE @Concat2a = @cats.Keys
                    .Concat
                    (@dogs.Keys);

// Method 1b
DECLARE @Concat2b = @cats.Select(c => c.Key)
                    .Concat
                    (@dogs.Select(d => d.Key));

// Method 2
DECLARE @Concat3 = from x in @cats.Keys
                   .Concat
                   (@dogs.Keys)
                   select x;

// Contrast with Union
DECLARE @Union = @cats.Keys
                 .Union
                 (@dogs.Keys);



@result1 =
    SELECT T.key AS key,
            T.value AS value
    FROM @table
    CROSS APPLY EXPLODE (@Concat1) AS T(key, value);

@result2a =
    SELECT T.value AS value
    FROM @table
    CROSS APPLY EXPLODE (@Concat2a) AS T(value);

@result2b =
    SELECT T.value AS value
    FROM @table
    CROSS APPLY EXPLODE (@Concat2b) AS T(value);

@result3 =
    SELECT T.value AS value
    FROM @table
    CROSS APPLY EXPLODE (@Concat3) AS T(value);

@result4 =
    SELECT T.value AS value
    FROM @table
    CROSS APPLY EXPLODE (@Union) AS T(value);




// Aternative method
// An alternative way of concatenating two sequences is to construct a collection, for example an array, of sequences and then apply the SelectMany<TSource, TResult> method, passing it the identity selector function.
DECLARE @alt = new [] { @cats.Select(x => x.Key), 
                        @dogs.Select(x => x.Key) 
                      }
                      .SelectMany(x => x);

@result5 =
    SELECT T.value AS value
    FROM @table
    CROSS APPLY EXPLODE (@alt) AS T(value);

// additional example
@result6 =
    SELECT T.value AS value
    FROM @table 
    CROSS APPLY EXPLODE (cats.Concat(dogs)) AS T(value);

// Alternative native method
@result7 =
    SELECT T.value AS value FROM @table CROSS APPLY EXPLODE (cats) AS T(value)
    UNION ALL
    SELECT T.value AS value FROM @table CROSS APPLY EXPLODE (dogs) AS T(value);


OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Concat/example1.txt"
USING Outputters.Tsv();

OUTPUT @result2a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Concat/example2a.txt"
USING Outputters.Tsv();

OUTPUT @result2b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Concat/example2b.txt"
USING Outputters.Tsv();

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Concat/example3.txt"
USING Outputters.Tsv();

OUTPUT @result4
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Concat/example4.txt"
USING Outputters.Tsv();

OUTPUT @result5
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Concat/example5.txt"
USING Outputters.Tsv();

OUTPUT @result6
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Concat/example6.txt"
USING Outputters.Tsv();

OUTPUT @result7
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Concat/example7.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Concat (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.concat)
* [UNION and OUTER UNION Expression (U-SQL)](union-and-outer-union-expression-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)
