---
title: "LongCount (Method Syntax in U-SQL) | Microsoft Docs"
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

# LongCount (Method Syntax in U-SQL)
Returns an [Int64](https://docs.microsoft.com/dotnet/api/system.int64) that represents the number of elements in a sequence.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**LongCount\<TSource>(IEnumerable\<TSource>)**   
Returns an `Int64` that represents the total number of elements in a sequence.  
The following code example demonstrates how to use LongCount\<TSource>(IEnumerable\<TSource>) to count the elements in an array.
```sql
// Create array larger than Int32.MaxValue
DECLARE @array = Enumerable.Range(0, Int32.MaxValue)
                .Concat(Enumerable.Range(0, 1));

@result1 =
    SELECT  @array.LongCount() AS longCountNumbers
            // , @array.Count() AS willFAIL
    FROM (VALUES(1)) AS A(x);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/LongCount/example1.txt"
USING Outputters.Tsv();
```

**LongCount\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>)**   
Returns an `Int64` that represents how many elements in a sequence satisfy a condition.  
The following code example demonstrates how to use LongCount\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>) to count the elements in an array that satisfy a condition.
```sql
@table = 
SELECT * FROM 
    ( VALUES
    (new SQL.MAP<string, bool?>{ {"Barley", true} , {"Boots", false}, {"Whiskers", false} })
    ) AS T(pets);
    
@result2 =
    SELECT  pets
           .LongCount(x => x.Value == false) AS count_UnvaccinatedPets
    FROM @table;

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/LongCount/example2.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.LongCount (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.longcount)
* [COUNT (U-SQL)](count-u-sql.md)
* [Count (Method Syntax in U-SQL)](count-method-syntax-in-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 