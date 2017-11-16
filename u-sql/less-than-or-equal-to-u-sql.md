---
title: "&lt;= (Less Than or Equal To) (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-27"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e1e9f00c-b3c1-44a5-b817-cf13613054cb
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# &lt;= (Less Than or Equal To) (U-SQL)
Compares two expressions (a comparison operator). When you compare nonnull expressions, the result is TRUE if the left operand has a value lower than or equal to the right operand; otherwise, the result is FALSE. 

<table><th align="left">Syntax</th><tr><td><pre>
Less_Than_or_Equal_To_Operator :=                                                                        
     <a href="#expr">expression</a> '&#60;=' <a href="#expr">expression</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements    
- <a name="expr"></a>**`expression`**  
  Is any valid expression. Both expressions must have implicitly convertible data types. 

### Return Type
Boolean.

### Examples   
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Less Than or Equal To with Numeric and Temporal Types**   
```
@somePeople = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",    100, (int?)10000, new DateTime(2012,05,31)),
        (2, "Sophia",  100, (int?)15000, new DateTime(2012,03,19)),
        (3, "Liam",    100, (int?)30000, new DateTime(2014,09,14)),
        (6, "Emma",    200, (int?)8000,  new DateTime(2014,03,08)),
        (7, "Jacob",   200, (int?)8000,  new DateTime(2014,09,02)),
        (8, "Olivia",  200, (int?)8000,  new DateTime(2013,12,11)),
        (9, "Mason",   300, (int?)50000, new DateTime(2016,01,01)),
        (10, "",       400, (int?)15000, new DateTime(2014,09,14)),
        (11, "Ethan ", 400, (int?)null,  new DateTime(2015,08,22))
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate);

// All records where Salary is 10,000 or less.
@result = SELECT * FROM @somePeople WHERE Salary <= 10000;
OUTPUT @result TO "/ReferenceGuide/Operators/Comparison/lessThan1.txt" USING Outputters.Tsv();

// All records where StartDate is 03/08/2014 or sooner
@result = SELECT * FROM @somePeople WHERE StartDate <= new DateTime(2014,03,08);
OUTPUT @result TO "/ReferenceGuide/Operators/Comparison/lessThan2.txt" USING Outputters.Tsv();
```

### See Also   
* [Operators (U-SQL)](operators-u-sql.md)
* [Simple Built-In U-SQL Types](simple-built-in-u-sql-types.md)
