---
title: "Any (Method Syntax in U-SQL) | Microsoft Docs"
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

# Any (Method Syntax in U-SQL)
Determines whether any element of a sequence exists or satisfies a condition.

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

**Any\<TSource> with SELECT**  
Used in SELECT to return True when owner has any pets.
```sql
@result1 =
    SELECT  LastName,
            petsMap.Any() AS anyPets
    FROM @table;

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Any/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Any\<TSource> with WHERE**  
Used in WHERE to return LastName when owner has any pets.
```sql
@result2 =
    SELECT LastName
    FROM   @table
    WHERE  petsMap.Any();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Any/example2.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Any\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>) with SELECT**   
Determines whether any element of a sequence satisfies a condition.  
Used in SELECT to return True when any pet name in sequence start with "B", else false.
```sql
@result3 =
    SELECT  LastName,
            petsArray.Any(x => x.StartsWith("B")) AS AnyPetStartsWithB_Array,
            petsMap.Any(x => x.Key.StartsWith("B")) AS AnyPetStartsWithB_Map,

            // alternative method for SQL.MAP
            petsMap.Keys.Any(x => x.StartsWith("B")) AS Any_petsStartsWithB_Map2 
    FROM @table;

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Any/example3.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Any\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>) with WHERE**   
Determines whether any element of a sequence satisfies a condition.  
Used in WHERE to return LastName when any pet name in sequence start with "B".
```sql
@result4 =
    SELECT LastName
    FROM   @table
    WHERE  petsArray.Any(x => x.StartsWith("B"));
    // WHERE  petsMap.Any(x => x.Key.StartsWith("B"));
    // WHERE petsMap.Keys.Any(x => x.StartsWith("B"));     // alternative method for SQL.MAP

OUTPUT @result4
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Any/example4.txt"
USING Outputters.Tsv();
```

**Any\<TSource>(IEnumerable\<TSource>, Func<TSource, Boolean>) - Additional Example**  
A variation of the above examples; here `Any` is used in the predicate of an Enumerable.Where clause.
```sql
// Method 1
@result5a =
    SELECT LastName, value AS petNames
    FROM   @table
    CROSS APPLY EXPLODE (petsArray
                         .Where(x => petsArray.Any(z => z.StartsWith("B")))
                        ) AS T(value);

// Method 2
@result5b =
    SELECT LastName, value AS petNames
    FROM   @table
    CROSS APPLY EXPLODE (from x in petsArray
                         where petsArray.Any(z => z.StartsWith("B"))
                         select x
                        ) AS T(value);

OUTPUT @result5a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Any/example5a.txt"
USING Outputters.Tsv();

OUTPUT @result5b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Any/example5b.txt"
USING Outputters.Tsv();
```

 **Any\<TSource> against nested values** 
```sql
// Dataset
@tableC = 
    SELECT * FROM 
    ( VALUES
    (1, new SQL.MAP<string, SQL.MAP<string, int?>>{
                {"Haas", new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} } } }),
    (2, new SQL.MAP<string, SQL.MAP<string, int?>>{
                {"Haas2", new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14} } } }),
    (3, new SQL.MAP<string, SQL.MAP<string, int?>>{
                {"Fakhouri", new SQL.MAP<string, int?>{ {"Snowball", 1} } } }),
    (4, new SQL.MAP<string, SQL.MAP<string, int?>>{
                {"Antebi", new SQL.MAP<string, int?>{ {"Belle", 8} } } }),
    (5, new SQL.MAP<string, SQL.MAP<string, int?>>{
                {"Philips", new SQL.MAP<string, int?>{ {"Sweetie", 2}, {"Rover", 13} } } }),
    (6, new SQL.MAP<string, SQL.MAP<string, int?>>{
                {"James", new SQL.MAP<string, int?>() } })
    ) AS T(id, person);


// Used in SELECT to return True when any pet name in sequence start with "B", else false.
@resultC1 =
    SELECT   id,
             person
            .SelectMany(v => v.Value)
            .Any(x => x.Key.StartsWith("B")) AS anyB
    FROM @tableC;

OUTPUT @resultC1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Any/complex1.txt"
USING Outputters.Tsv();


// Used in the predicate of an Enumerable.Where clause 
// Owner name is returned when any name in the sequence starts with B.
@resultC2 =
    SELECT  T.value AS anyB
    FROM @tableC
    CROSS APPLY EXPLODE (person
                         .Where(x => x.Value.Any(z => z.Key.StartsWith("B")))
                         .Select(x => x.Key)
                        ) AS T(value);

OUTPUT @resultC2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Any/complex2.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Any (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.any)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)
