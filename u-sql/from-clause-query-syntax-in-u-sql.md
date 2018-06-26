---
title: "from clause (Query Syntax in U-SQL) | Microsoft Docs"
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

# from clause (Query Syntax in U-SQL)
A query expression must begin with a `from` clause. Additionally, a query expression can contain sub-queries, which also begin with a `from` clause.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Basic Syntax**  
In the following example, `@numbers` is the data source and `num` is the range variable. 
```sql
// A simple data source.
DECLARE @numbers = new SQL.ARRAY<int>{ 5, 4, 1, 3, 9, 8, 6, 7, 2, 0 };

// Create the query.
// @lowNums is an IEnumerable<int>
DECLARE @lowNums = from num in @numbers
                   where num < 5
                   select num;

// Execute the query.
@result1a = 
    SELECT T.value AS lowNums
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@lowNums) AS T(value);

// Alternative native method
@result1b = 
    SELECT T.value AS lowNums
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@numbers) AS T(value)
    WHERE value < 5;

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/From/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/From/example1b.txt"
USING Outputters.Tsv();
```

**Compound from Clauses**  
```sql
DECLARE @students = new SQL.MAP<string, SQL.ARRAY<int>>{
                                    {"Omelchenko", new SQL.ARRAY<int> {97, 72, 81, 60}}, 
                                    {"O'Donnell", new SQL.ARRAY<int> {75, 84, 91, 39}}, 
                                    {"Mortensen", new SQL.ARRAY<int> {88, 94, 65, 85}},
                                    {"Garcia", new SQL.ARRAY<int> {97, 89, 85, 82}},
                                    {"Beebe", new SQL.ARRAY<int> {35, 72, 91, 70}}
                                    };

// Method 1
DECLARE @scoreQuery2a = from student in @students
                        from score in student.Value
                        where score > 90
                        select new KeyValuePair<string, int>(student.Key, score);

// Method 2
DECLARE @scoreQuery2b = (from student in @students
                         from score in student.Value
                         where score > 90
                         select new { Last = student.Key, score })
                        .ToDictionary(x => x.Last, x => x.score);

// Alternative native method
 @result2c = 
    SELECT  T.key AS student,
            S.value AS score
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@students) AS T(key, list)
    CROSS APPLY EXPLODE(list) AS S(value)
    WHERE S.value > 90;


@result2a = 
    SELECT  T.key AS student,
            T.value AS score
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@scoreQuery2a) AS T(key, value);

@result2b = 
    SELECT  T.key AS student,
            T.value AS score
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@scoreQuery2b) AS T(key, value);

OUTPUT @result2a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/From/example2a.txt"
USING Outputters.Tsv();

OUTPUT @result2b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/From/example2b.txt"
USING Outputters.Tsv();

OUTPUT @result2c
TO "/ReferenceGuide/cSharp/LINQ/Keywords/From/example2c.txt"
USING Outputters.Tsv();
```

**Using Multiple from Clauses to Perform Joins**
```sql
DECLARE @upperCase = new SQL.ARRAY<char>{ 'A', 'B', 'C' };
DECLARE @lowerCase = new SQL.ARRAY<char>{ 'x', 'y', 'z' };

DECLARE @joinQuery3a =
            from upper in @upperCase
            from lower in @lowerCase
            select new SQL.ARRAY<char>{ upper, lower };

// Alternative native method
@result3b = 
    SELECT  S.value AS upper,
            T.value AS lower
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@upperCase) AS S(value)
    CROSS APPLY EXPLODE(@lowerCase) AS T(value);


@result3a = 
    SELECT  T.value[0] AS upper,
            T.value[1] AS lower
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@joinQuery3a) AS T(value);

OUTPUT @result3a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/From/example3a.txt"
USING Outputters.Tsv(charFormat: "string");

OUTPUT @result3b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/From/example3b.txt"
USING Outputters.Tsv(charFormat: "string");
```

## See Also
* [from clause (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/from-clause)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)