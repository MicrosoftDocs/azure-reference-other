---
title: "IF...ELSE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-04-26"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ecf15797-d5db-453a-9361-204db6558ed8
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# IF...ELSE (U-SQL)
Imposes conditions on the execution of a U-SQL statement which is evaluated at compile time. The U-SQL statement that follows an IF keyword and its condition is executed if the condition is satisfied: the Boolean expression returns TRUE. The optional ELSE keyword introduces another U-SQL statement that is executed when the IF condition is not satisfied: the Boolean expression returns FALSE.

The Boolean expression has to be compile-time constant foldable, such as the value passed as a parameter.

<table><th align="left">Syntax</th><tr><td><pre>
If_Else_Statement :=                                                                                      
    'IF' <a href="#bool_expr">Boolean_Expression</a> 'THEN'
         <a href="query-statements-and-expressions-u-sql.md">U-SQL_Statement</a> 
    [ 'ELSEIF' <a href="#bool_expr">Boolean_Expression</a> 'THEN'
         <a href="query-statements-and-expressions-u-sql.md">U-SQL_Statement</a> ]
    [ 'ELSE' <a href="#bool_expr">Boolean_Expression</a> 'THEN'
         <a href="query-statements-and-expressions-u-sql.md">U-SQL_Statement</a> ]
'END'.
</pre></td></tr></table>

### Semantics of Syntax Elements    
- <a name="bool_expr"></a>**`Boolean_Expression`**  
Is a constant-foldable expression that returns TRUE or FALSE.    

### Examples    
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  

**Dataset**   
```
@employees = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",   100, (int?)10000, new DateTime(2012,05,31), "cell:030-0074321,office:030-0076545"),
        (2, "Sophia", 100, (int?)15000, new DateTime(2012,03,19), "cell:(5) 555-4729,office:(5) 555-3745"),
        (3, "Liam",   100, (int?)30000, new DateTime(2014,09,14), "cell:(5) 555-3932"),
        (4, "Amy",    100, (int?)35000, new DateTime(1999,02,27), "cell:(171) 555-7788,office:(171) 555-6750, home:(425) 555-6238"),
        (5, "Justin", 100, (int?)15000, new DateTime(2015,01,12), "cell:0921-12 34 65,office:0921-12 34 67"),
        (6, "Emma",   200, (int?)8000,  new DateTime(2014,03,08), (string)null),
        (7, "Jacob",  200, (int?)8000,  new DateTime(2014,09,02), ""),
        (8, "Olivia", 200, (int?)8000,  new DateTime(2013,12,11), "cell:88.60.15.31,office:88.60.15.32"),
        (9, "Mason",  300, (int?)50000, new DateTime(2016,01,01), "cell:(91) 555 22 82,office:(91) 555 91 99, home:(425) 555-2819"),
        (10, "Ava",   400, (int?)15000, new DateTime(2014,09,14), "cell:91.24.45.40,office:91.24.45.41"),
        (11, "Ethan", 400, (int?)9000,  new DateTime(2015,08,22), "cell:(604) 555-4729,office:(604) 555-3745"),
        (12, "David", 800, (int?)100,   new DateTime(2016,11,01), "cell:(171) 555-1212"),
        (13, "Andrew", 100, (int?)null, new DateTime(1995,07,16), "cell:(1) 135-5555,office:(1) 135-4892"),
        (14, "Jennie", 100, (int?)34000, new DateTime(2000,02,12), "cell:(5) 555-3392,office:(5) 555-7293")
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate, PhoneNumbers);
```

**One condition**   
```
DECLARE @DeptID int = 100;

IF @DeptID == 100 THEN
    @result = SELECT * FROM @employees WHERE DeptID == 100;
END;

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/ControlOfFlow/IF/ExampleA.csv"
USING Outputters.Csv();
```

**One condition and ELSE**   
```
DECLARE @DeptID int = 100;

IF @DeptID == 200 THEN
    @result =  SELECT * FROM @employees WHERE DeptID = 200;
ELSE 
    @result =  SELECT * FROM @employees WHERE DeptID == @DeptID;
END;

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/ControlOfFlow/IF/ExampleB.csv"
USING Outputters.Csv();
```

**Two conditions and ELSE**   
```
DECLARE @DeptID int = 100;

IF @DeptID == 200 THEN
    @result =  SELECT * FROM @employees WHERE DeptID = 200;
ELSEIF @DeptID == 100 THEN
    @result = SELECT * FROM @employees WHERE DeptID == 100;
ELSE 
    @result =  SELECT * FROM @employees WHERE DeptID == @DeptID;
END;

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/ControlOfFlow/IF/ExampleC.csv"
USING Outputters.Csv();
```

**Nested conditions**   
```
DECLARE @DeptID int = 100;
DECLARE @flag bool = true;

IF @DeptID == 100 
THEN
    IF @flag == true 
    THEN
        @result =  SELECT * FROM @employees WHERE DeptID == 100 AND Salary >= 30000;
    END;
ELSEIF @DeptID == 200 
THEN
    @result = SELECT * FROM @employees WHERE DeptID == 200;
ELSE 
    @result =  SELECT * FROM @employees WHERE DeptID == @DeptID;
END;

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/ControlOfFlow/IF/ExampleD.csv"
USING Outputters.Csv();
```

## See Also
* [Query Statements and Expressions (U-SQL)](../u-sql/query-statements-and-expressions-u-sql.md)
* [Common SQL Expressions in U-SQL](../u-sql/common-sql-expressions-in-u-sql.md)
* [Built-in Functions (U-SQL)](../u-sql/built-in-functions-u-sql.md) 
