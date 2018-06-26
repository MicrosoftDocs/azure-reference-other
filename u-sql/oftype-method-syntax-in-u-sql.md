---
title: "OfType (Method Syntax in U-SQL) | Microsoft Docs"
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

# OfType (Method Syntax in U-SQL)
Filters the elements of an [IEnumerable](https://docs.microsoft.com/dotnet/api/system.collections.ienumerable)  based on a specified type.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**OfType\<TResult>(IEnumerable)**  
The following code example demonstrates how to use OfType\<TResult> to filter the elements of an IEnumerable.
```sql
// Dataset
DECLARE @items = new System.Collections.ArrayList{ "Snowball", 11, 3.33, null, 8, 3.33m, "Belle", DateTime.Now};

// Method 1
DECLARE @query1 = @items
                 .OfType<string>();

// Method 2 (Alternative usage with query syntax)
DECLARE @query2 = from x in @items
                 .OfType<DateTime>()
                  select x;

// Method 3
@result3 =
    SELECT T.value AS ints
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@items.OfType<int>()) AS T(value);


@result1 =
    SELECT T.value AS strings
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1) AS T(value);

@result2 =
    SELECT T.value AS dateTime
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query2) AS T(value);


OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/OfType/example1.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/OfType/example2.txt"
USING Outputters.Tsv();

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/OfType/example3.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.OfType (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.oftype)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)