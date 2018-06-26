---
title: "where clause | Microsoft Docs"
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

# where clause
The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Basic Syntax**  
In the following example, `@numbers` is the data source and `num` is the range variable. 
```sql
// A simple data source.
DECLARE @numbers = new SQL.ARRAY<int>{ 5, 4, 1, 3, 9, 8, 6, 7, 2, 0 };

// Simple query with one predicate in where clause.
DECLARE @queryLowNums = from num in @numbers
                        where num < 5
                        select num;

// Execute the query.
@result1a = 
    SELECT T.value AS queryLowNums
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@queryLowNums) AS T(value);

// Alternative native method
@result1b = 
    SELECT T.value AS queryLowNums
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@numbers) AS T(value)
    WHERE value < 5;

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/Where/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/Where/example1b.txt"
USING Outputters.Tsv();
```

**Multiple predicates in where clause**  
```sql
DECLARE @queryLowNums2a =
            from num in @numbers
            where num < 5 && num % 2 == 0
            select num;

// Alternative native method
@result2b = 
    SELECT T.value AS queryLowNums
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@numbers) AS T(value)
    WHERE value < 5 AND value % 2 == 0;


@result2a = 
    SELECT T.value AS queryLowNums
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@queryLowNums2a) AS T(value);

OUTPUT @result2a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/Where/example2a.txt"
USING Outputters.Tsv();

OUTPUT @result2b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/Where/example2b.txt"
USING Outputters.Tsv();
```


**Multiple where clauses**  
```sql
DECLARE @queryLowNums3 =
            from num in @numbers
            where num < 5 
            where num % 2 == 0
            select num;

@result3 = 
    SELECT T.value AS queryLowNums
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@queryLowNums3) AS T(value);

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/Keywords/Where/example3.txt"
USING Outputters.Tsv();
```

**Where clause containing a method that returns a Boolean value**
```sql
DECLARE @words = new SQL.ARRAY<string>{"Alpha", "Bravo", "", "Delta", "Echo"};

// Create the query with a method call in the where clause.
DECLARE @queryWords =
            from word in @words
            where !string.IsNullOrWhiteSpace(word)
            select word;

// Alternative native method
@result4b = 
    SELECT T.value AS queryWords
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@words) AS T(value)
    WHERE !string.IsNullOrWhiteSpace(value);


@result4a = 
    SELECT T.value AS queryWords
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE(@queryWords) AS T(value);

OUTPUT @result4a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/Where/example4a.txt"
USING Outputters.Tsv();

OUTPUT @result4b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/Where/example4b.txt"
USING Outputters.Tsv();
```


## See Also
* [where clause (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/where-clause)
* [Where (Method Syntax in U-SQL)](where-method-syntax-in-u-sql.md)
* [WHERE Clause (U-SQL)](where-clause-u-sql.md)
* [Enumerable.Where (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.where)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)