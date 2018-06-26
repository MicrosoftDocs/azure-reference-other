---
title: "Range (Method Syntax in U-SQL) | Microsoft Docs"
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

# Range (Method Syntax in U-SQL)
Generates a sequence of integral numbers within a specified range.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**Range(Int32, Int32)**  
The following code example demonstrates how to use Range to generate a sequence of values.  
```sql
@result1 =
    SELECT T.value AS rangedValues
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (Enumerable.Range(1, 10)) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Range/example1.txt"
USING Outputters.Tsv();
```

**Range and additional computation**  
Generate a sequence of integers from 1 to 10 and then select their squares.
```sql
@result2 =
    SELECT T.value AS rangedValues
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (Enumerable.Range(1, 10).Select(x => x * x)) AS T(value);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Range/example2.txt"
USING Outputters.Tsv();
```

**Additional examples**  
```sql
// Method 1
DECLARE @range1 = Enumerable.Range(1, 10)
                 .Select(x => x * x);

// Method 2 (Alternative usage with query syntax)
DECLARE @range2 = from x in Enumerable.Range(1, 10)
                  select x * x;

@result3 =
    SELECT T.value AS rangedValues
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@range1) AS T(value);

@result4 =
    SELECT T.value AS rangedValues
    FROM (VALUES(1)) AS A(x)
    CROSS APPLY EXPLODE (@range2) AS T(value);

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Range/example3.txt"
USING Outputters.Tsv();

OUTPUT @result4
TO "/ReferenceGuide/cSharp/LINQ/EnumerableMethods/Range/example4.txt"
USING Outputters.Tsv();
```

## See Also
* [Enumerable.Range (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.range)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)