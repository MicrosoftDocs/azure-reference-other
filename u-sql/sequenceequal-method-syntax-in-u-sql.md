---
title: "SequenceEqual (Method Syntax in U-SQL) | Microsoft Docs"
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

# SequenceEqual (Method Syntax in U-SQL)
Determines whether two sequences are equal according to an equality comparer.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The example(s) below are based on the dataset(s) defined below.  Ensure your execution includes the rowset variable(s).  

**Dataset**   
```sql
@table = 
    SELECT * FROM 
    ( VALUES
    ("Haas",     new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} },
                                                                             new SQL.ARRAY<string>{"Barley", "Boots", "Whiskers"}),
    ("Fakhouri", new SQL.MAP<string, int?>{ {"Snowball", 1} },               new SQL.ARRAY<string>{"Belle"}),
    ("Antebi",   new SQL.MAP<string, int?>{ {"Belle", 8} },                  new SQL.ARRAY<string>{"BELLE"}),
    ("Philips",  new SQL.MAP<string, int?>{ {"Sweetie", 2}, {"Belle", 8}, {"Rover", 13} }, 
                                                                             new SQL.ARRAY<string>{"Belle", "Sweetie", "Rover"}),
    ("James",    new SQL.MAP<string, int?>(),                                new SQL.ARRAY<string>())
    ) AS T(LastName, petsMap, petsArray);
```

**SequenceEqual\<TSource>(IEnumerable\<TSource>, IEnumerable\<TSource>) with `SELECT`**  
Determines whether two sequences are equal by comparing the elements by using the default equality comparer for their type.  
Returns true if the two source sequences are of equal length and their corresponding elements are equal according to the default equality comparer for their type; otherwise, false.  
The following code examples demonstrate how to use SequenceEqual\<TSource>(IEnumerable\<TSource>, IEnumerable\<TSource>) to determine whether two sequences are equal.
```sql
// Used in SELECT to return True when sequences are equal, else false.
@result1 =
    SELECT  LastName,
            petsMap.Keys.SequenceEqual(petsArray) AS sequenceEqual
    FROM @table;

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SequenceEqual/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```

**SequenceEqual\<TSource>(IEnumerable\<TSource>, IEnumerable\<TSource>) with `WHERE`**  
```sql
// Used in WHERE to return LastName when sequences are equal.
@result2 =
    SELECT LastName
    FROM   @table
    WHERE  petsMap.Keys.SequenceEqual(petsArray);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SequenceEqual/example2.txt"
USING Outputters.Tsv();
```

**Additional examples**   
```sql
// Dataset
DECLARE @pet1 = new SQL.MAP<string, int?>{ {"Turbo", 2} };
DECLARE @pet2 = new SQL.MAP<string, int?>{ {"Peanut", 8} };

DECLARE @pets1 = new SQL.ARRAY<SQL.MAP<string, int?>> {@pet1, @pet2};
DECLARE @pets2 = new SQL.ARRAY<SQL.MAP<string, int?>> {@pet1, @pet2};
DECLARE @pets3 = new SQL.ARRAY<SQL.MAP<string, int?>>{
                        new SQL.MAP<string, int?>{ {"Turbo", 2} },
                        new SQL.MAP<string, int?>{ {"Peanut", 8} }
                        };

@result3 =
    SELECT  @pets1.SequenceEqual(@pets2) AS sequenceEqual,
            @pets1.SequenceEqual(@pets3) AS sequenceEqual2
    FROM (VALUES(1)) AS A(x);

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/SequenceEqual/example3.txt"
USING Outputters.Tsv(outputHeader: true);
```

## See Also
* [Enumerable.SequenceEqual (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.sequenceequal)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)