---
title: "DefaultIfEmpty (Method Syntax in U-SQL) | Microsoft Docs"
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

# DefaultIfEmpty (Method Syntax in U-SQL)
Returns the elements of an [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1), or a default valued singleton collection if the sequence is empty.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset(s) defined below.

**Dataset**  
```sql
@table = 
SELECT * FROM 
    ( VALUES
    ( new SQL.ARRAY<int>{}, new SQL.ARRAY<int>{9})
    ) AS T(empty, nonEmpty);
```

**DefaultIfEmpty\<TSource>(IEnumerable\<TSource>)**  
Returns the elements of the specified sequence or the type parameter's default value in a singleton collection if the sequence is empty.  
The following code examples demonstrate how to use DefaultIfEmpty\<TSource>(IEnumerable\<TSource>) to provide a default value in case the source sequence is empty.
```sql
@result1 =
    SELECT  T.value AS w_DefaultIfEmpty_empty
    FROM @table
    CROSS APPLY EXPLODE (empty.DefaultIfEmpty()) AS T(value);

@result2 =
    SELECT  T.value AS wo_DefaultIfEmpty_empty
    FROM @table
    CROSS APPLY EXPLODE (empty) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/DefaultIfEmpty/example1.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/DefaultIfEmpty/example2.txt"
USING Outputters.Tsv();


@result3 =
    SELECT  T.value AS w_DefaultIfEmpty_nonEmpty
    FROM @table
    CROSS APPLY EXPLODE (nonEmpty.Concat(empty.DefaultIfEmpty())) AS T(value);

@result4 =
    SELECT  T.value AS wo_DefaultIfEmpty_nonEmpty
    FROM @table
    CROSS APPLY EXPLODE (nonEmpty.Concat(empty)) AS T(value);

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/DefaultIfEmpty/example3.txt"
USING Outputters.Tsv();

OUTPUT @result4
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/DefaultIfEmpty/example4.txt"
USING Outputters.Tsv();
```


**DefaultIfEmpty\<TSource>(IEnumerable\<TSource>, TSource)**  
Returns the elements of the specified sequence or the specified value in a singleton collection if the sequence is empty.  
The following code example demonstrates how to use the DefaultIfEmpty\<TSource>(IEnumerable\<TSource>, TSource) method and specify a default value - 3.
```sql
@result5 =
    SELECT  T.value AS DefaultIfEmpty
    FROM @table
    CROSS APPLY EXPLODE (empty.DefaultIfEmpty(3)) AS T(value);

OUTPUT @result5
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/DefaultIfEmpty/example5.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.DefaultIfEmpty (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.defaultifempty)
* [Enumerable.Empty (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.empty)
* [Empty (Method Syntax in U-SQL)](empty-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)