---
title: "% (Modulo) (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-27"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 0f19aad5-86f0-4af1-995f-d87d4a94f4e1
caps.latest.revision: 3
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# % (Modulo) (U-SQL)
Returns the remainder of one number divided by another.

<table><th>Syntax</th><tr><td><pre>
Modulo_Operator :=                                                                                       
    <a href="#dividend">dividend </a> '%' <a href="#divisor">divisor</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements    
-   <a name="dividend"></a>**`dividend`**  
Is the numeric expression to divide. dividend must be a valid expression of any one of the data types in the integer and monetary data type categories, or the numeric data type.

-   <a name="divisor"></a>**`divisor`**  
Is the numeric expression by which to divide the dividend. divisor must be any valid expression of any one of the data types in the integer and monetary data type categories, or the numeric data type.

### Return Type
Determined by data types of the two arguments.

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Simple Example**  
The following example divides the number 38 by 5. This results in 7 as the integer portion of the result and demonstrates how modulo returns the remainder of 3. 
```
@aValue = 
    SELECT * FROM 
        ( VALUES
        (38)
        ) AS T(col1);

@result =
    SELECT 38 / 5 AS Integer,
           38 % 5 AS Remainder,
           col1 % 5 AS Remainder2
    FROM @aValue;

OUTPUT @result
TO "/Output/ReferenceGuide/Operators/Arithmetic/Modulo1.txt"
USING Outputters.Csv();
```

### See Also
* [Built-in Functions (U-SQL)](../USQL/built-in-functions-u-sql.md)
* [Operators (U-SQL)](../USQL/operators-u-sql.md)

