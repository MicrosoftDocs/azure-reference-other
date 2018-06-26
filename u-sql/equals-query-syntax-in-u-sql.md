---
title: "equals (Query Syntax in U-SQL) | Microsoft Docs"
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

# equals (Query Syntax in U-SQL)
The `equals` contextual keyword is used in a [join](join-clause-query-syntax-in-u-sql.md) clause in a query expression to compare the elements of two sequences.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
 
**Basic Example**  
```sql
// Datasets
DECLARE @categories = new SQL.MAP<int, string>{
                            {001, "Beverages"},
                            {002, "Condiments"},
                            {003, "Vegetables"},
                            {004, "Grains"},
                            {005, "Fruit"}            
                            };

DECLARE @products = new SQL.MAP<string, int?>{
                          {"Cola", 001},
                          {"Tea", 001},
                          {"Mustard", 002},
                          {"Pickles", 002},
                          {"Carrots", 003},
                          {"Bok Choy", 003},
                          {"Peaches", 005},
                          {"Melons", 005}
                          };

// Query
DECLARE @innerJoinQuery =
    from category in @categories
    join prod in @products 
    on category.Key equals prod.Value
    select new SQL.ARRAY<string>{ prod.Key, category.Value };

@result1 = 
        SELECT  T.value[0] AS productName,
                T.value[1] AS categoryName              
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@innerJoinQuery) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/Keywords/equals/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```


## See Also
* [equals (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/equals)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)