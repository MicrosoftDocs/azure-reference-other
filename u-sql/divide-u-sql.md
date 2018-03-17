---
title: "(Divide) (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/27/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b73eec71-0ba9-4fd7-91c5-a73a60467131
caps.latest.revision: 3
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# / (Divide) (U-SQL)
Divides one [number](numeric-types-and-literals.md) by another (an arithmetic division operator). 

<table><th align="left">Syntax</th><tr><td><pre>
Divide_Operator :=                                                                                       
    <a href="#expr">dividend</a> '/' <a href="#divisor">divisor</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements    
-   <a name="expr"></a>**`dividend`**  
One of the [Numeric Types](numeric-types-and-literals.md) to divide.

-   <a name="divisor"></a>**`divisor`**  
One of the [Numeric Types](numeric-types-and-literals.md) by which to divide the dividend.

### Return Type
Returns the data type of the argument with the higher precedence.  If an integer dividend is divided by an integer divisor, the result is an integer that has any fractional part of the result truncated. 


### Examples   
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Divide with Numeric Types**  
```sql
@data = 
    SELECT * FROM 
        ( VALUES
        ((int)25)
        ) AS T(aNumber);

DECLARE @val int = 5;

@result =
    SELECT 25 / 5 AS Int1,
           aNumber / 5 AS Int2,
           aNumber / @val AS Int3,
           aNumber / 3 AS truncatedResult,
           aNumber / 3.0 AS toDouble,
           aNumber / (int?)null AS intNull           
           // aNumber / 0 AS divideByZero  // will error
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/Operators/Arithmetic/Divide1.txt"
USING Outputters.Csv();
```

### See Also
* [Operators (U-SQL)](operators-u-sql.md)
* [Numeric Types and Literals](numeric-types-and-literals.md)






