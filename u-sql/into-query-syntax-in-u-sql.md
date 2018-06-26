---
title: "into (Query Syntax in U-SQL) | Microsoft Docs"
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

# into (Query Syntax in U-SQL)
The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](group-clause-query-syntax-in-u-sql.md), [join](join-clause-query-syntax-in-u-sql.md) or [select](select-clause-query-syntax-in-u-sql.md) clause into a new identifier. 

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Basic Syntax** 
```sql
DECLARE @employees = new SQL.MAP<string, string>{ {"Bob", "Sales"}, {"Susan", "Sales"}, {"Willis", "Management"},
                                                  {"Sean", "Sales"}, {"Jennifer", "Management"}, {"Michael", "IT"}
                                                };

DECLARE @query1a = (from x in @employees
                   group x by x.Value into gb 
                   select gb)
                  .ToDictionary(k => k.Key, v => v.Count());

// Alternative native method
@result1b = 
        SELECT T.value AS Department,
               COUNT(T.key) AS EmployeeCount               
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@employees) AS T(key, value)
        GROUP BY T.value;

@result1a = 
        SELECT T.key AS Department,
               T.value AS EmployeeCount
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@query1a) AS T(key, value);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/into/example1a.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/into/example1b.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Additional Example**   
```sql
DECLARE @words  = new string[]{ "apples", "blueberries", "oranges", "bananas", "apricots"};

DECLARE @query2 = (from w in @words
                  group w by w[0] into fruitGroup
                  where fruitGroup.Count() >= 2
                  select fruitGroup)
                 .ToDictionary(k => k.Key, v => v.Count());

@result2 = 
        SELECT string.Format("{0} has {1} elements.", T.key, T.value) AS firstLetterGroup,
               T.key + " has " + T.value.ToString() + " elements." AS firstLetterGroup2
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@query2) AS T(key, value);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/Keywords/into/example2.txt"
USING Outputters.Tsv(outputHeader: true);
```
 
## See Also
* [into (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/into)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)
