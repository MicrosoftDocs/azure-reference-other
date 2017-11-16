---
title: "== (Equals) (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-04-12"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c46f3414-ff87-4688-8c7e-391cf0e8480e
caps.latest.revision: 5
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# == (Equals) (U-SQL)
Compares the equality of two expressions (a comparison operator).
U-SQL uses C# null semantics which is 2-valued and not 3-valued as in ANSI SQL.

<table><th align="left">Syntax</th><tr><td><pre>
Equals_Operator :=                                                                                       
    <a href="#expr">expression</a> == <a href="#expr">expression</a>.
</pre></td></tr></table>

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


/********** Working with null **********/
// Does return a record (non ANSI  behavior)
@result1 = SELECT * FROM @somePeople WHERE Salary == null;
OUTPUT @result1 TO "/Output/ReferenceGuide/Operators/Comparison/example1.txt" USING Outputters.Tsv();

// Does return a record
@result2 = SELECT * FROM @somePeople WHERE Salary == (int?)null;
OUTPUT @result2 TO "/Output/ReferenceGuide/Operators/Comparison/example2.txt" USING Outputters.Tsv();

// Does return a record
@result3 = SELECT * FROM @somePeople WHERE Salary IS NULL;
OUTPUT @result3 TO "/Output/ReferenceGuide/Operators/Comparison/example3.txt" USING Outputters.Tsv();

// Result set includes a record with a null salary (non ANSI  behavior)
@result4 = SELECT * FROM @somePeople WHERE Salary != 8000;
OUTPUT @result4 TO "/Output/ReferenceGuide/Operators/Comparison/example4.txt" USING Outputters.Tsv();
/***************************************/


// Other examples
@result5 = SELECT * FROM @somePeople WHERE EmpName.TrimEnd() == "Ethan";
OUTPUT @result5 TO "/Output/ReferenceGuide/Operators/Comparison/example5.txt" USING Outputters.Tsv();

@result6 = SELECT * FROM @somePeople WHERE EmpName == "Ethan ";
OUTPUT @result6 TO "/Output/ReferenceGuide/Operators/Comparison/example6.txt" USING Outputters.Tsv();

// Empty space is not equal to null
@result7 = SELECT * FROM @somePeople WHERE EmpName == null;
OUTPUT @result7 TO "/Output/ReferenceGuide/Operators/Comparison/example7.txt" USING Outputters.Tsv();

// Empty space is not equal to white space
@result8 = SELECT * FROM @somePeople WHERE EmpName == " ";
OUTPUT @result8 TO "/Output/ReferenceGuide/Operators/Comparison/example8.txt" USING Outputters.Tsv();
```

### See Also
* [Data Types and Literals (U-SQL)](data-types-and-literals-u-sql.md)   
* [Operators (U-SQL)](operators-u-sql.md)
