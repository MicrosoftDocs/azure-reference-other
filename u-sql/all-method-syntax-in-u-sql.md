---
title: "All (Method Syntax in U-SQL) | Microsoft Docs"
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

# All (Method Syntax in U-SQL)
Determines whether all elements of a sequence satisfy a condition.  Returns true if every element of the source sequence passes the test in the specified predicate, or if the sequence is empty; otherwise, false.

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
    ("Haas2",     new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}},
                                                                             new SQL.ARRAY<string>{"Barley", "Boots"}),
    ("Fakhouri", new SQL.MAP<string, int?>{ {"Snowball", 1} },               new SQL.ARRAY<string>{"Snowball"}),
    ("Antebi",   new SQL.MAP<string, int?>{ {"Belle", 8} },                  new SQL.ARRAY<string>{"Belle"}),
    ("Philips",  new SQL.MAP<string, int?>{ {"Sweetie", 2}, {"Rover", 13} }, new SQL.ARRAY<string>{"Sweetie", "Rover"}),
    ("James",    new SQL.MAP<string, int?>(),                                new SQL.ARRAY<string>())
    ) AS T(LastName, petsMap, petsArray);
```
 
 **All\<TSource> with SELECT**  
 Used in SELECT to return True when all pet names in sequence start with "B", else false.  Note treatment of empty sequence, James.
```sql
@result1 =
    SELECT  LastName,
            petsArray.All(x => x.StartsWith("B")) AS All_petsStartsWithB_Array,
            petsMap.All(x => x.Key.StartsWith("B")) AS All_petsStartsWithB_Map,

            // alternative method for SQL.MAP
            petsMap.Keys.All(x => x.StartsWith("B")) AS All_petsStartsWithB_Ma2
    FROM @table;

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/example1.txt"
USING Outputters.Tsv();
```

 **All\<TSource> with WHERE**  
 Used in WHERE to return LastName when all pet names in sequence start with "B".  Note treatment of empty sequence, James.
```sql
@result2 =
    SELECT LastName
    FROM   @table
    WHERE  petsArray.All(x => x.StartsWith("B"));  
    // WHERE  petsMap.All(x => x.Key.StartsWith("B"));  
    // WHERE  petsMap.Keys.All(x => x.StartsWith("B"));  // alternative method for SQL.MAP

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/example2.txt"
ORDER BY LastName
USING Outputters.Tsv();
```

 **All\<TSource> - Additional Example**  
A variation of the above examples; here `All` is used in the predicate of an Enumerable.Where clause   
All pet names are returned when all names in the sequence starts with B.
```sql
// Method 1
@result3a =
    SELECT LastName, value AS petNames
    FROM   @table
    CROSS APPLY EXPLODE (petsArray
                         .Where(x => petsArray.All(z => z.StartsWith("B")))
                        ) AS T(value);

// Method 2
@result3b =
    SELECT LastName, value AS petNames
    FROM   @table
    CROSS APPLY EXPLODE (from x in petsArray
                         where petsArray.All(z => z.StartsWith("B"))
                         select x
                        ) AS T(value);


OUTPUT @result3a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/example3a.txt"
USING Outputters.Tsv();

OUTPUT @result3b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/example3b.txt"
USING Outputters.Tsv();
```

 **All\<TSource> against nested values** 
```sql
// Dataset
DECLARE @people = 
    new SQL.MAP<string, SQL.MAP<string, int?>>{
                {"Haas", new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} } },
                {"Haas2", new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14} } },
                {"Fakhouri", new SQL.MAP<string, int?>{ {"Snowball", 1} } },
                {"Antebi", new SQL.MAP<string, int?>{ {"Belle", 8} } },
                {"Philips", new SQL.MAP<string, int?>{ {"Sweetie", 2}, {"Rover", 13} } },
                {"James", new SQL.MAP<string, int?>() }
            };


// returns T or F (Method 1a)
DECLARE @a1 = from x in @people
              select x.Value.All(z => z.Key.StartsWith("B"));

// returns names
DECLARE @a11 = from x in @people
               where x.Value.All(z => z.Key.StartsWith("B"))
               select x.Key;

// returns both
DECLARE @a111 = from x in @people
                let a = x.Value.All(z => z.Key.StartsWith("B")).ToString()
                select new SQL.ARRAY<string>{x.Key, a};


// returns T or F (Method 1b)
DECLARE @a2 = from x in @people.Values
              select x.Keys.All(z => z.StartsWith("B"));

// returns T or F (Method 1c)
DECLARE @a3 = from x in @people.Values
              select x.All(z => z.Key.StartsWith("B"));


// returns T or F (Method 2a)
DECLARE @b1 = @people
              .Select(x => x.Value.All(z => z.Key.StartsWith("B")));

// returns names
DECLARE @b11 = @people
              .Where(x => x.Value.All(z => z.Key.StartsWith("B")))
              .Select(x => x.Key);

// returns both
DECLARE @b111 = @people
                .Select(x => new SQL.ARRAY<string>{ x.Key, x.Value.All(z => z.Key.StartsWith("B")).ToString() } );

// returns T or F (Method 2b)
DECLARE @b2 = @people.Values
              .Select(x => x.Keys.All(z => z.StartsWith("B")));

// returns T or F (Method 2c)
DECLARE @b3 = @people.Values
              .Select(x => x.All(z => z.Key.StartsWith("B")));


@resulta1 =
    SELECT  T.value AS all_nestedKeysVariable1
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@a1) AS T(value);

@resulta11 =
    SELECT  T.value AS all_nestedKeysVariable1
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@a11) AS T(value);

@resulta111 =
    SELECT  T.value[0] AS all_nestedKeysVariable1,
            T.value[1] AS bbb
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@a111) AS T(value);

@resulta2 =
    SELECT  T.value AS all_nestedKeysVariable1
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@a2) AS T(value);

@resulta3 =
    SELECT  T.value AS all_nestedKeysVariable1
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@a3) AS T(value);


@resultb1 =
    SELECT  T.value AS all_nestedKeysVariable1
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@b1) AS T(value);

@resultb11 =
    SELECT  T.value AS all_nestedKeysVariable1
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@b11) AS T(value);

@resultb111 =
    SELECT  T.value[0] AS all_nestedKeysVariable1,
            T.value[1] AS bbb
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@b111) AS T(value);

@resultb2 =
    SELECT  T.value AS all_nestedKeysVariable1
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@b2) AS T(value);

@resultb3 =
    SELECT  T.value AS all_nestedKeysVariable1
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@b3) AS T(value);


OUTPUT @resulta1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/a1.txt"
USING Outputters.Tsv();

OUTPUT @resulta11
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/a11.txt"
USING Outputters.Tsv();

OUTPUT @resulta111
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/a111.txt"
USING Outputters.Tsv();

OUTPUT @resulta2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/a2.txt"
USING Outputters.Tsv();

OUTPUT @resulta3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/a3.txt"
USING Outputters.Tsv();


OUTPUT @resultb1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/b1.txt"
USING Outputters.Tsv();

OUTPUT @resultb11
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/b11.txt"
USING Outputters.Tsv();

OUTPUT @resultb111
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/b111.txt"
USING Outputters.Tsv();

OUTPUT @resultb2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/b2.txt"
USING Outputters.Tsv();

OUTPUT @resultb3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/All/b3.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.All (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.all)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)
