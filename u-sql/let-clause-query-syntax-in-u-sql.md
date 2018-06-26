---
title: "let clause (Query Syntax in U-SQL) | Microsoft Docs"
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

# let clause (Query Syntax in U-SQL)
In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses. 

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Basic Example**  
In the following example `let` is used in two ways:
1) To create an enumerable type that can itself be queried.
2) To enable the query to call `ToLower` only one time on the range variable `word`. Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.
```sql
// Dataset
DECLARE @strings = new SQL.ARRAY<string>
                { "A penny saved is a penny earned.",
                  "The early bird catches the worm.",
                  "The pen is mightier than the sword." 
                };

// Query
DECLARE @earlyBirdQuery =
            from sentence in @strings
            let words = sentence.Split(' ')
            from word in words
            let w = word.ToLower()
            where w[0] == 'a' || w[0] == 'e'
                || w[0] == 'i' || w[0] == 'o'
                || w[0] == 'u'
            select word;

@result1 = 
        SELECT  T.value AS wordsStartingWithVowels           
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@earlyBirdQuery) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/Keywords/let/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```

## See Also
* [let clause (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/let-clause)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)
