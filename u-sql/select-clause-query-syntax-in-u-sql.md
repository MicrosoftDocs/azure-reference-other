---
title: "select clause (Query Syntax in U-SQL) | Microsoft Docs"
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

# select clause (Query Syntax in U-SQL)
In a query expression, the `select` clause specifies the type of values that will be produced when the query is executed.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Basic Syntax**   
```sql
DECLARE @numbers = new SQL.ARRAY<int>{ 5, 4, 1, 3, 9, 8, 6, 7, 2, 0 };

DECLARE @query1 = from x in @numbers
                  select x;

@result1a =
    SELECT T.value AS numbers
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query1) AS T(value);

// Alternative native method
@result1b =
    SELECT T.value AS numbers
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@numbers) AS T(value);
    
OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/select/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/select/example1b.txt"
USING Outputters.Tsv();
 ```


**Select mutiple values**  
```sql
DECLARE @TimeZoneInfo = TimeZoneInfo.GetSystemTimeZones().Take(10); 

DECLARE @query2 = from x in @TimeZoneInfo
                  select new SQL.ARRAY<string>{x.Id, x.DisplayName};

@result2 =
    SELECT  T.value[0] AS Id,
            T.value[1] AS DisplayName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query2) AS T(value);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/Keywords/select/example2.txt"
USING Outputters.Tsv();
```

**Selecting from SQL.MAPs**  
```sql
DECLARE @pets = new SQL.MAP<string, int?>{ {"Barley", 10}, {"Boots", 14}, {"Whiskers", 6} };

// Selecting the entire SQL.MAP
DECLARE @query3a = from x in @pets
                   select x;

// Selecting only the Keys
DECLARE @query3b = from x in @pets
                   select x.Key;

@result3a =
    SELECT  T.key AS petName,
            T.value AS petAge
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query3a) AS T(key, value);

@result3b =
    SELECT  T.key AS petName
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@query3b) AS T(key);

OUTPUT @result3a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/select/example3a.txt"
USING Outputters.Tsv();

OUTPUT @result3b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/select/example3b.txt"
USING Outputters.Tsv();
```

## See Also
* [select clause (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/select-clause)
* [Select (Method Syntax in U-SQL)](select-method-syntax-in-u-sql.md)
* [SELECT Clause (U-SQL)](select-clause-u-sql.md)
* [Enumerable.Select (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.select)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)