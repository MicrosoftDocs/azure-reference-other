---
title: "!= (Not Equal To) (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-27"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 7fa982b9-2a55-428b-a3ba-6ded68d85905
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# != (Not Equal To) (U-SQL)
Tests whether one expression is not equal to another expression (a comparison operator). 

<table><th>Syntax</th><tr><td><pre>
Not_Equal_To:=                                                                                           
    <a href="#expr">expression</a> != <a href="#expr">expression</a>.
</pre></td></tr></table>

> [!NOTE]
> U-SQL uses C# null semantics which is 2-valued and not 3-valued as in ANSI SQL.

### Semantics of Syntax Elements    
-   <a name="expr"></a>**`expression`**  
Is any valid expression. If the expressions are not of the same data type, the data type for one expression must be implicitly convertible to the data type of the other. 

### Result Types
[Boolean](other-simple-built-in-types-and-literals.md) 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

```
@somePeople = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",    100, (int?)10000, new DateTime(2012,05,31), "cell:030-0074321,office:030-0076545"),
        (2, "Sophia",  100, (int?)15000, new DateTime(2012,03,19), "cell:(5) 555-4729,office:(5) 555-3745"),
        (3, "Liam",    100, (int?)30000, new DateTime(2014,09,14), ""),
        (6, "Emma",    200, (int?)8000,  new DateTime(2014,03,08), (string)null),
        (7, "Jacob",   200, (int?)8000,  new DateTime(2014,09,02), "cell:(5) 555-3932"),
        (8, "Olivia",  200, (int?)8000,  new DateTime(2013,12,11), "cell:88.60.15.31,office:88.60.15.32"),
        (9, "Mason",   300, (int?)50000, new DateTime(2016,01,01), "cell:(91) 555 22 82,office:(91) 555 91 99, home:(425) 555-2819"),
        (10, "",       400, (int?)15000, new DateTime(2014,09,14), "cell:91.24.45.40,office:91.24.45.41"),
        (11, "Ethan ", 400, (int?)null,  new DateTime(2015,08,22), "cell:(604) 555-4729,office:(604) 555-3745")
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate, PhoneNumbers);


// Returns all records where Salary does not contain a null value (non ANSI  behavior)
@result1 = SELECT * FROM @somePeople WHERE Salary != null;
OUTPUT @result1 TO "/Output/ReferenceGuide/Operators/Comparison/Inequality1.txt" USING Outputters.Tsv();

// Returns all records where Salary does not contain a null value
@result2 = SELECT * FROM @somePeople WHERE Salary IS NOT NULL;
OUTPUT @result2 TO "/Output/ReferenceGuide/Operators/Comparison/Inequality2.txt" USING Outputters.Tsv();

// Returns all records where Salary is not 8000 or null (non ANSI  behavior)
@result3 = SELECT * FROM @somePeople WHERE Salary != 8000;
OUTPUT @result3 TO "/Output/ReferenceGuide/Operators/Comparison/Inequality3.txt" USING Outputters.Tsv();
```

### See Also
* [Data Types and Literals (U-SQL)](data-types-and-literals-u-sql.md) 
* [Operators (U-SQL)](operators-u-sql.md)
    
    
    
    