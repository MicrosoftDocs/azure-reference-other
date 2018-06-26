---
title: "ToArray (Method Syntax in U-SQL) | Microsoft Docs"
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

# ToArray (Method Syntax in U-SQL)
Creates an array from an [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1)  .

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
 
 **ToArray\<TSource>(IEnumerable\<TSource>)**    
Returns an array that contains the elements from the input sequence.  
The following code example demonstrates how to use ToArray\<TSource> to force immediate query evaluation and return an array of results.
```sql
// Dataset
DECLARE @pets = new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6}, {"Belle", 8} };


// Method 1
DECLARE @newArray1 = @pets
                    .Keys.ToArray();

// Method 2 (Using Query Syntax)
DECLARE @newArray2 = from x in @pets
                    .Keys.ToArray()
                     select x;


@result1 =
    SELECT T.value AS petNames
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@newArray1) AS T(value);

@result2 =
    SELECT T.value AS petNames
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@newArray2) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ToArray/example1.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/ToArray/example2.txt"
USING Outputters.Tsv();
```
 
 
## See Also
* [Enumerable.ToArray (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.toarray)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)