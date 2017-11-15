---
title: "* (Multiply) (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-27"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e9f1b5f6-4d97-49c1-954e-481d0b719a56
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# * (Multiply) (U-SQL)
Multiplies two expressions (an arithmetic multiplication operator). 

<table><th align="left">Syntax</th><tr><td><pre>
Multiply_Operator :=                                                                                     
     <a href="#expr">expression</a> '*' <a href="#expr">expression</a>.
</pre></td></tr></table>

  
### Semantics of Syntax Elements    
-   <a name="expr"></a>**`expression`**  
One of the [Numeric Types](../USQL/numeric-types-and-literals.md).

### Return Type
Returns the data type of the argument with the higher precedence.


### Examples  
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Multiply with Numeric Types**  
```
@data = 
    SELECT * FROM 
        ( VALUES
        ((int)38)
        ) AS T(aNumber);

DECLARE @val int = 5;

@result =
    SELECT 38 * 5 AS Int1,
           aNumber * 5 AS Int2,
           aNumber * @val AS Int3,
           aNumber * (int?)null AS intNull,
           (aNumber * (double)12345).GetType().Name AS intAndDouble,
           (aNumber * (long)12345).GetType().Name AS intAndLong
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/Operators/Arithmetic/Multiply1.txt"
USING Outputters.Csv();
```

### See Also
* [Operators (U-SQL)](../USQL/operators-u-sql.md)
* [Aggregate Functions (U-SQL)](../USQL/aggregate-functions-u-sql.md)
* [Numeric Types and Literals](../USQL/numeric-types-and-literals.md)



