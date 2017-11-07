---
title: "CSHARP (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: bb97801f-95f3-4fc4-9820-9e3b025bba39
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CSHARP (U-SQL)
U-SQL’s tight integration with C#’s expression language normally makes calls to C# expression seamless. On rare occasions it may be useful to be able to guard a C# expression from getting interpreted by U-SQL, such as when a new version of C# may introduce a syntax that conflicts with an established U-SQL syntax or when the C# expression needs to turn off U-SQL name binding or U-SQL reserved keywords in the expression. 


<table><th>Syntax</th><tr><td><pre>
CSHARP_Expression :=                                                                                     
    'CSHARP' '(' <a href="#exp">expression</a> ')'.  
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="exp"></a>**`expression`**    
The C# expression to be guarded as pure C# expression without U-SQL name resolutions or syntax interpretations.  

### Return Type 
Polymorphic based on the expression’s type. 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  

**Dataset**   
```
@aCircle = 
    SELECT * FROM 
        ( VALUES
        (3)
        ) AS T(radius);
```
The following query fails because PI is an uppercase name and thus a reserved keyword: 
```
@result =
    SELECT Math.PI * radius * radius AS Area
    FROM @aCircle; 
```

The CSHARP function turns off the keyword reservation and allows to use PI: 
```
@result =
    SELECT CSHARP(Math.PI) * radius * radius AS Area
    FROM @aCircle;

OUTPUT @result
TO "/Output/ReferenceGuide/Operators/Other/csharp1.txt"
USING Outputters.Csv();
```
### See Also 
* [Built-in Functions (U-SQL)](../USQL/built-in-functions-u-sql.md)  
* [C# Functions and Operators (U-SQL)](../USQL/csharp-functions-and-operators-u-sql.md) 
