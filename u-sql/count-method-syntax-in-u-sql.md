---
title: "Count (Method Syntax in U-SQL) | Microsoft Docs"
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

# Count (Method Syntax in U-SQL)
Returns the number of elements in a sequence.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset(s) defined below.

**Dataset**   
```sql
@table = 
SELECT * FROM 
    ( VALUES
    (new SQL.ARRAY<int>{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}, 
            new SQL.MAP<string, bool?>{ {"Barley", true} , {"Boots", false}, {"Whiskers", false} })
    ) AS T(numbers, pets);
```

**Count\<TSource>(IEnumerable\<TSource>)**  
Returns the number of elements in a sequence.  
The following code example demonstrates how to use Count\<TSource>(IEnumerable\<TSource>) to count the elements in an array.
```sql
@result1 =
    SELECT  numbers.Count() AS countNumbers,
            pets.Count() AS countPets
    FROM @table;

// Alternative native method
@result1a =
    SELECT  COUNT(T.value) AS countNumbers
    FROM @table
    CROSS APPLY EXPLODE (numbers) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Count/example1.txt"
USING Outputters.Tsv();

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Count/example1a.txt"
USING Outputters.Tsv();
```

**Count\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>)**  
Returns a number that represents how many elements in the specified sequence satisfy a condition.  
The following code example demonstrates how to use Count\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>) to count the elements in an array that satisfy a condition.
```sql
@result2 =
    SELECT  pets
           .Count(x => x.Value == false) AS count_UnvaccinatedPets
    FROM @table;

// Alternative native method
@result2a =
    SELECT  COUNT(T.value) AS count_UnvaccinatedPets
    FROM @table
    CROSS APPLY EXPLODE (pets) AS T(key, value)
    WHERE value == false;

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Count/example2.txt"
USING Outputters.Tsv();

OUTPUT @result2a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Count/example2a.txt"
USING Outputters.Tsv();
```


## See Also
* [Enumerable.Count (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.count)
* [Enumerable.LongCount (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.longcount)
* [COUNT (U-SQL)](count-u-sql.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)