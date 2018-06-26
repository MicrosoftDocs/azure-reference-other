---
title: "Contains (Method Syntax in U-SQL) | Microsoft Docs"
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

# Contains (Method Syntax in U-SQL)
Determines whether a sequence contains a specified element.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset(s) defined below.

**Dataset**  
```sql
@table = 
    SELECT * FROM 
    ( VALUES
    ("Haas",     new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} },
                                                                             new SQL.ARRAY<string>{"Barley", "Boots", "Whiskers"}),
    ("Fakhouri", new SQL.MAP<string, int?>{ {"Snowball", 1} },               new SQL.ARRAY<string>{"Snowball"}),
    ("Antebi",   new SQL.MAP<string, int?>{ {"Belle", 8} },                  new SQL.ARRAY<string>{"Belle"}),
    ("Philips",  new SQL.MAP<string, int?>{ {"Sweetie", 2}, {"Rover", 13} }, new SQL.ARRAY<string>{"Sweetie", "Rover"}),
    ("James",    new SQL.MAP<string, int?>(),                                new SQL.ARRAY<string>())
    ) AS T(LastName, petsMap, petsArray);
```

**Contains\<TSource>(IEnumerable\<TSource>, TSource) with SELECT**  
Determines whether a sequence contains a specified element by using the default equality comparer.
Used in `SELECT` to return True when an owner owns a pet named "Belle", else False.
```sql
@result1 =
    SELECT  LastName,

            // Method 1
            petsMap
            .Select(x => x.Key)
            .Contains("Belle") AS containsBelle_Map_Lambda,

            // Method 2 (Alternative usage with query syntax)
            (from x in petsMap
            select x.Key)
            .Contains("Belle") AS containsBelle_Map,

            petsArray.Contains("Belle") AS containsBelle_Array
    FROM @table;    

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Contains/example1.txt"
USING Outputters.Tsv(outputHeader: true);


// Alternative Method
@result1a =
    SELECT  DISTINCT LastName,
            M.key.Contains("Belle") AS containsBelle_Map,
            A.key.Contains("Belle") AS containsBelle_Array
    FROM @table
    CROSS APPLY EXPLODE (petsArray) AS A(key)
    CROSS APPLY EXPLODE (petsMap) AS M(key, value);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Contains/example1a.txt"
USING Outputters.Tsv();
```

**Contains\<TSource>(IEnumerable\<TSource>, TSource) with WHERE**  
Determines whether a sequence contains a specified element by using the default equality comparer.
Used in `WHERE` to return `LastName` for owners that own a pet named "Belle".
```sql
// Method 1
@result2a =
    SELECT LastName
    FROM  @table
    WHERE petsMap.Select(x => x.Key).Contains("Belle");

// Method 2 (Alternative usage with query syntax)
@result2b =
    SELECT LastName
    FROM  @table
    WHERE (from x in petsMap select x.Key).Contains("Belle");

OUTPUT @result2a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Contains/example2a.txt"
USING Outputters.Tsv();

OUTPUT @result2b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Contains/example2b.txt"
USING Outputters.Tsv();


// Additional examples
@result2c =
    SELECT LastName
    FROM @table
    WHERE petsArray.Contains("Belle");

@result2d =
    SELECT LastName
    FROM @table
    // CROSS APPLY EXPLODE (petsArray) AS T(key)
    CROSS APPLY EXPLODE (petsMap) AS T(key, value)
    WHERE key.Contains("Belle");

OUTPUT @result2c
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Contains/example2c.txt"
USING Outputters.Tsv();

OUTPUT @result2d
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Contains/example2d.txt"
USING Outputters.Tsv();
```

**Searching against a list of names**   
```sql
DECLARE @pets = new SQL.ARRAY<string>{"Belle", "Toby", "Rover"};

@result3 =
    SELECT LastName
    FROM @table
    //CROSS APPLY EXPLODE (petsArray) AS T(key)
    CROSS APPLY EXPLODE (petsMap) AS T(key, value)
    WHERE @pets.Contains(key);

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Contains/example3.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Contains (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.contains)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md) 
