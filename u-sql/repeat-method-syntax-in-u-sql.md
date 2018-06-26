---
title: "Repeat (Method Syntax in U-SQL) | Microsoft Docs"
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

# Repeat (Method Syntax in U-SQL)
Generates a sequence that contains one repeated value.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**Repeat\<TResult>(TResult, Int32)**  
Returns an IEnumerable\<T> that contains a repeated value.  
The following code example demonstrates how to use Repeat\<TResult> to generate a sequence of a repeated value.
```sql
// Dataset
@table = 
    SELECT * FROM 
        ( VALUES
        ("Another World")
        ) AS T(col1);

// Query
@result1 =
    SELECT T.value AS repeatedValues
    FROM @table
    CROSS APPLY EXPLODE (Enumerable.Repeat(col1, 7)) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Repeat/example1.txt"
USING Outputters.Tsv();
```

**Additional examples**  
```sql
// Dataset
DECLARE @repeatedValues = Enumerable.Repeat("Hello World", 5);

@result2 =
    SELECT T.value AS repeatedValues
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@repeatedValues) AS T(value);

@result3 =
    SELECT T.value AS repeatedValues
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (Enumerable.Repeat("Hello World", 3)) AS T(value);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Repeat/example2.txt"
USING Outputters.Tsv();

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Repeat/example3.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Repeat (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.repeat)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)