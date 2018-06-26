---
title: "Empty (Method Syntax in U-SQL) | Microsoft Docs"
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

# Empty (Method Syntax in U-SQL)
Returns an empty [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1) that has the specified type argument.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Empty\<TResult>()**  
The following code example demonstrates how to use Empty\<TResult>() to generate an empty IEnumerable\<T>.
```sql
DECLARE @empty IEnumerable<decimal> = Enumerable.Empty<decimal>();
```
**Empty\<TResult>() - Additional Example**  
The following code example demonstrates a possible application of the Empty\<TResult>() method.   
The Aggregate\<TSource> method is applied to a collection of string arrays.     
The elements of each array in the collection are added to the resulting IEnumerable\<T> only if that array contains four or more elements. 
Empty\<TResult> is used to generate the seed value for Aggregate\<TSource> because if no array in the collection has four or more elements, only the empty sequence is returned.
```sql
DECLARE @names1 = new SQL.ARRAY<string>{"Tommy"};
DECLARE @names2 = new SQL.ARRAY<string>{"Terry", "Henriette Thaulow", "Magnus", "Shu"};
DECLARE @names3 = new SQL.ARRAY<string>{"Ajay", "Helge", "Henriette Thaulow", "Cristina", "Lucio"};
DECLARE @namesList = new List<SQL.ARRAY<string>>{@names1, @names2, @names3};

DECLARE @query2 = @namesList
                  .Aggregate(Enumerable.Empty<string>(),
                        (current, next) => next.Count > 3 ? current.Union(next) : current);

@result2 =
    SELECT  T.value AS value
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@query2) AS T(value);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Empty/example2.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Empty (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.empty)
* [Enumerable.DefaultIfEmpty (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.defaultifempty)
* [DefaultIfEmpty (Method Syntax in U-SQL)](defaultifempty-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)