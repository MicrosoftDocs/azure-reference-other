---
title: "Cast (Method Syntax in U-SQL) | Microsoft Docs"
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

# Cast (Method Syntax in U-SQL)
Casts the elements of an [IEnumerable](https://docs.microsoft.com/dotnet/api/system.collections.ienumerable) to the specified type.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Cast\<TResult>**  
The following code example demonstrates how to use Cast\<TResult>(IEnumerable) to enable the use of the standard query operators on an [ArrayList](https://docs.microsoft.com/dotnet/api/system.collections.arraylist). 
The following code, without the cast, doesn't compile.
Without cast you will receive an error similiar to the following:
    `E_CSC_USER_INVALIDCSHARP: C# error CS1934: 
    Could not find an implementation of the query pattern for source type 'System.Collections.ArrayList'.  'OrderBy' not found.  
    Consider explicitly specifying the type of the range variable 'fruit'`.
```sql
// Dataset
DECLARE @fruits = new System.Collections.ArrayList{"mango", "apple", "lemon"};

                
DECLARE @query1 = @fruits
                  .Cast<string>()   // Execute with this line commented to reveal error
                  .OrderBy(fruit => fruit)
                  .Select(fruit => fruit);

// Method used with query syntax (Alternative)
DECLARE @query2 = from fruit in @fruits 
                  .Cast<string>()   // Execute with this line commented to reveal error
                  orderby fruit ascending 
                  select fruit;

@result1 =
    SELECT T.value AS fruit
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1) AS T(value);

@result2 =
    SELECT T.value AS fruit
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query2) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Cast/example1.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Cast/example2.txt"
USING Outputters.Tsv();
```


## See Also
* [Enumerable.Cast (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.cast)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)
