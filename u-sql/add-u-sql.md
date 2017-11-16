---
title: "+ (Add) (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-27"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 88db94df-4d72-41d0-b216-164ed7a25437
caps.latest.revision: 3
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# + (Add) (U-SQL)
Adds two [numbers](numeric-types-and-literals.md), [temporal types](temporal-types-and-literals.md), or concatenates two [strings](textual-types-and-literals.md).

<table><th>Syntax</th><tr><td><pre>
Add_Operator :=                                                                                          
    <a href="#expr">expression</a> '+' <a href="#expr">expression</a>.
</pre></td></tr></table>

  
### Semantics of Syntax Elements    
-   <a name="expr"></a>**`expression`**  
Is the expression to add. 

### Return Type
Returns the data type of the argument with the higher precedence.


### Examples   
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Add with Numeric and Textual Types**   
```
@data = 
    SELECT * FROM 
        ( VALUES
        (38, "aString", "38")
        ) AS T(aNumber, aString, anotherString);

DECLARE @val int = 5;

@result =
    SELECT 38 + 5 AS Int1,
           aNumber + 5 AS Int2,
           aNumber + @val AS Int3,
           aNumber.ToString() + aString AS string1,
           aString + " anotherString" AS string2,
           aString + 23 AS string3, // int is implicitly converted to string
           anotherString + 23 AS string4,
           aNumber + "23" AS string5,   
           1 + 1 AS numberAndNumber,
           1 + "1" AS numberAndString,
           "1" + "1" AS stringAndString,
           aNumber + (int?)null AS intNull,
           aString + (string)null AS stringNull
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/Operators/Arithmetic/Add1.txt"
USING Outputters.Csv();
```

**Add with Temporal Types**   
```
@data = 
    SELECT * FROM 
        ( VALUES
        (new DateTime(2016,05,31))
        ) AS T(aDate);

@result =
    SELECT aDate + new System.TimeSpan(1, 0, 0, 0) AS date1,
          (new TimeSpan(1, 0, 0, 0) + new TimeSpan(0, 1, 0, 0)).ToString() AS date2
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/Operators/Arithmetic/Add2.txt"
USING Outputters.Csv();
```

### See Also
* [Operators (U-SQL)](operators-u-sql.md)
* [Date & Time](csharp-functions-and-operators-u-sql.md#DateTime)
* [Simple Built-In U-SQL Types](simple-built-in-u-sql-types.md)

