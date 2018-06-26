---
title: "GroupBy (Method Syntax in U-SQL) | Microsoft Docs"
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

# GroupBy (Method Syntax in U-SQL)
Groups the elements of a sequence.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Basic Example**   
```sql
// Dataset
DECLARE @employees = new SQL.MAP<string, string>{ {"Bob", "Sales"}, {"Susan", "Sales"}, {"Willis", "Management"},
                                                  {"Sean", "Sales"}, {"Jennifer", "Management"}, {"Michael", "IT"}
                                                };

// Method 1
DECLARE @query1 = (from x in @employees
                  group x by x.Value)
                 .ToDictionary(k => k.Key, v => v.Count());

// Method 1a
DECLARE @query1a = (from x in @employees
                   group x by x.Value into gb 
                   select gb)
                  .ToDictionary(k => k.Key, v => v.Count());

// Method 2
DECLARE @query2 =  @employees
                  .GroupBy(x => x.Value)
                  .ToDictionary(k => k.Key, v => v.Count());

// Alternative native method
@result3 = 
        SELECT T.value AS Department,
               COUNT(T.key) AS EmployeeCount               
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@employees) AS T(key, value)
        GROUP BY T.value;



@result1 = 
        SELECT T.key AS Department,
               T.value AS EmployeeCount
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@query1) AS T(key, value);

@result1a = 
        SELECT T.key AS Department,
               T.value AS EmployeeCount
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@query1a) AS T(key, value);

@result2 = 
        SELECT T.key AS Department,
               T.value AS EmployeeCount
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@query2) AS T(key, value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/GroupBy/A/example1.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/GroupBy/A/example1a.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/GroupBy/A/example2.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/GroupBy/A/example3.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Additional Examples** 
```sql
@table = 
SELECT * FROM 
    ( VALUES
    (new SQL.MAP<string, double?>{ {"Barley", 8.3}, {"Boots", 4.9}, {"Whiskers", 1.5}, {"Daisy", 4.3} })
    ) AS T(pets);
  
DECLARE @pets = new SQL.MAP<string, double?>{ {"Barley", 8.3}, {"Boots", 4.9}, {"Whiskers", 1.5}, {"Daisy", 4.3} };


// Groups the elements of a sequence according to a specified key selector function and creates a result value from each group and its key.
// Example based on c# example from https://msdn.microsoft.com/en-us/library/bb549393(v=vs.110).aspx
DECLARE @query4 = 
        @pets.GroupBy(
        pet => Math.Floor(pet.Value.GetValueOrDefault()),
        (age, pets) => new SQL.ARRAY<string>
        {
            "Age group: " + age. ToString(),
            "Number of pets in this age group: " + pets.Count().ToString(),
            "Minimum age: " + pets.Min(pet => pet.Value).ToString(),
            "Maximum age: " + pets.Max(pet => pet.Value).ToString(),
            "-------------"
        });

@result4 = 
    SELECT S.type AS GroupResult
    FROM @table
    CROSS APPLY EXPLODE (@query4) AS T(Group)
    CROSS APPLY EXPLODE (Group) AS S(type);

OUTPUT @result4
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/GroupBy/example4.txt"
USING Outputters.Tsv();
/**********************************************************************/



// Same results as above though with a typical horizontal layout
DECLARE @query4a = 
        @pets.GroupBy(
        pet => Math.Floor(pet.Value.GetValueOrDefault()),
        (age, pets) => new SQL.ARRAY<double?>
        {
            age,
            pets.Count(),
            pets.Min(pet => pet.Value),
            pets.Max(pet => pet.Value)
        });

@result4a = 
        SELECT  T.Group[0] AS ageGroup,
                T.Group[1] AS numberInGroup,
                T.Group[2] AS minimumAge,
                T.Group[3] AS maximumAge
    FROM @table
    CROSS APPLY EXPLODE (@query4a) AS T(Group);

OUTPUT @result4a
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/GroupBy/example4a.csv"
USING Outputters.Csv(outputHeader: true);
/**********************************************************************/



// Variant using data from table rather than a variable
@result4b = 
        SELECT  T.Group[0] AS ageGroup,
                T.Group[1] AS numberInGroup,
                T.Group[2] AS minimumAge,
                T.Group[3] AS maximumAge
    FROM @table
    CROSS APPLY EXPLODE (
                            pets.GroupBy(
                                pet => Math.Floor(pet.Value.GetValueOrDefault()),
                                (age, Gpets) => new SQL.ARRAY<double?>
                                {
                                    age,
                                    Gpets.Count(),
                                    Gpets.Min(pet => pet.Value),
                                    Gpets.Max(pet => pet.Value)
                                })
                        ) AS T(Group);

OUTPUT @result4b
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/GroupBy/example4b.csv"
USING Outputters.Csv(outputHeader: true);
/**********************************************************************/



// Alternative native method
@result4c = 
    SELECT  DISTINCT
            Math.Floor(T.value.GetValueOrDefault()) AS ageGroup,
            COUNT(T.value) OVER (PARTITION BY Math.Floor(T.value.GetValueOrDefault())) AS numberInGroup,
            MIN(T.value) OVER (PARTITION BY Math.Floor(T.value.GetValueOrDefault())) AS minimumAge,
            MAX(T.value) OVER (PARTITION BY Math.Floor(T.value.GetValueOrDefault())) AS maximumAge
    FROM @table
    CROSS APPLY EXPLODE (@pets) AS T(key, value);

OUTPUT @result4c
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/GroupBy/example4c.csv"
USING Outputters.Csv(outputHeader: true);
/**********************************************************************/




// Variation of above queries.
// Groups the elements of a sequence according to a specified key selector function and creates a result value from each group and its key. The elements of each group are projected by using a specified function.
// Example based on c# example from https://msdn.microsoft.com/en-us/library/bb534493(v=vs.110).aspx
DECLARE @query5 = 
        @pets.GroupBy(
        pet => Math.Floor(pet.Value.GetValueOrDefault()),
        pet => pet.Value,
        (baseAge, ages) => new SQL.ARRAY<string>
        {
            "Age group: " + baseAge.ToString(),
            "Number of pets in this age group: " + ages.Count().ToString(),
            "Minimum age: " + ages.Min(x => x.Value).ToString(),
            "Maximum age: " + ages.Max(x => x.Value).ToString(),
            "-------------"
        });

@result5 = 
    SELECT S.type AS GroupResult
    FROM @table
    CROSS APPLY EXPLODE (@query4) AS T(Group)
    CROSS APPLY EXPLODE (Group) AS S(type);

OUTPUT @result5
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/GroupBy/example5.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.GroupBy (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.groupby)
* [group clause (Query Syntax in U-SQL)](group-clause-query-syntax-in-u-sql.md)
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [group clause (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/group-clause)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)