---
title: "Join (Method Syntax in U-SQL) | Microsoft Docs"
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

# Join (Method Syntax in U-SQL)
Correlates the elements of two sequences based on matching keys.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Join<TOuter, TInner, TKey, TResult>(IEnumerable\<TOuter>, IEnumerable\<TInner>, Func<TOuter, TKey>, Func<TInner, TKey>, Func<TOuter, TInner, TResult>)**  
The following code example demonstrates how to use `Join` to perform an inner join of two sequences based on a common key.
```sql
// The queries below answer the question: Which available movie is also a Best Picture winner?

// Dataset
DECLARE @availableMovies = new SQL.ARRAY<string>{"Lady Bird", "Three Billboards Outside Ebbing, Missouri", "The Shape of Water", "La La Land", "Brooklyn"};
DECLARE @BestPictureWinners = new SQL.ARRAY<string>{"The Shape of Water", "Moonlight", "Spotlight"};


// Queries
// Method 1
DECLARE @query1a = @availableMovies
                   .Join(@BestPictureWinners, a => a, b => b, (a, b) => a);

// Method 2 (Query Syntax)
DECLARE @query1b =  from a in @availableMovies
                    join b in @BestPictureWinners 
                    on a equals b
                    select a;

// Alternative native method
@result2 = 
    SELECT T.am AS available_BestPicture
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@availableMovies) AS T(am)
    CROSS APPLY EXPLODE (@BestPictureWinners) AS S(bpm)
    WHERE am == bpm;


@result1a = 
    SELECT T.Group AS available_BestPicture
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1a) AS T(Group);

@result1b = 
    SELECT T.Group AS available_BestPicture
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1b) AS T(Group);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Join/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Join/example1b.txt"
USING Outputters.Tsv();

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Join/example2.txt"
USING Outputters.Tsv();
```

**Additional Example**  
```sql
// Dataset
DECLARE @people = new SQL.MAP<string, string>{
                            {"magnus", "Hedlund, Magnus"},
                            {"terry", "Adams, Terry"},
                            {"charlotte", "Weiss, Charlotte"}
                            };

DECLARE @pets = new SQL.MAP<string, string>{
                            {"Barley", "terry"},
                            {"Boots", "terry"},
                            {"Whiskers", "charlotte"},
                            {"Daisy", "magnus"}
                            };

// Queries
// Method 1
DECLARE @query3a = @people
                  .Join(@pets,
                        person => person.Key,
                        pet => pet.Value,
                        (person, pet) =>  new SQL.ARRAY<string> {
                                                person.Value,  pet.Key 
                                                }
                        );

// Method 2 (Query Syntax)
DECLARE @query3b = from a in @people
                   join b in @pets 
                   on a.Key equals b.Value
                   select new SQL.ARRAY<string>{a.Value, b.Key};

// Alternative method
DECLARE @query4 = from a in @people                    
                  from b in @pets 
                  where a.Key == b.Value
                  select new SQL.ARRAY<string>{a.Value, b.Key};


@result3a = 
    SELECT  T.Group[0] AS ownerName,
            T.Group[1] AS petName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query3a) AS T(Group);

@result3b = 
    SELECT  T.Group[0] AS ownerName,
            T.Group[1] AS petName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query3b) AS T(Group);

@result4 = 
    SELECT  T.Group[0] AS ownerName,
            T.Group[1] AS petName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query4) AS T(Group);
    
OUTPUT @result3a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Join/example3a.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result3b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Join/example3b.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result4
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Join/example4.txt"
USING Outputters.Tsv(outputHeader: true);
```


## See Also
* [Enumerable.Join (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.join)
* [join clause (Query Syntax in U-SQL)](join-clause-query-syntax-in-u-sql.md)
* [U-SQL SELECT Selecting from Joins](u-sql-select-selecting-from-joins.md)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)