---
title: "by (Query Syntax in U-SQL) | Microsoft Docs"
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

# by (Query Syntax in U-SQL)
The `by` contextual keyword is used in the [group](group-clause-query-syntax-in-u-sql.md) clause in a query expression to specify how the returned items should be grouped.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**Basic Example**  
```sql
// Datasets
DECLARE @employees = new SQL.MAP<string, string>{ {"Bob", "Sales"}, {"Susan", "Sales"}, {"Willis", "Management"},
                                                  {"Sean", "Sales"}, {"Jennifer", "Management"}, {"Michael", "IT"}
                                                };

// Queries
// Method 1
DECLARE @query1a = (from x in @employees
                   group x by x.Value)
                  .ToDictionary(k => k.Key, v => v.Count());

// Method 2
DECLARE @query1b = (from x in @employees
                   group x by x.Value into gb 
                   select gb)
                  .ToDictionary(k => k.Key, v => v.Count());

// Alternative native method
@result1c = 
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

@result1b = 
        SELECT T.key AS Department,
               T.value AS EmployeeCount
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@query1b) AS T(key, value);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/by/example1a.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/by/example1b.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result1c
TO "/ReferenceGuide/cSharp/LINQ/Keywords/by/example1c.txt"
USING Outputters.Tsv(outputHeader: true);
``` 
 
## See Also
* [by (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/by)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)