---
title: "IS NULL (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "09/27/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: bd5f06b8-4a89-4821-946a-4cb6cb357a35
caps.latest.revision: 2
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# IS NULL (U-SQL)
Determines whether a specified expression is NULL.  If the value of expression is NULL, IS NULL returns TRUE; otherwise, it returns FALSE.
If the value of expression is NULL, IS NOT NULL returns FALSE; otherwise, it returns TRUE.

<table><th align="left">Syntax</th><tr><td><pre>
Is_Null_Predicate :=                                                                                     
     <a href="#str_exp">string_expression</a> 'IS' ['<a href="#not">NOT</a>'] 'NULL'.
</pre></td></tr></table>
  
### Semantics of Syntax Elements    
- <a name="str_exp"></a>**`string_expression`**  
  is the expression that creates the string value to be tested.

- <a name="not"></a>**`NOT`**  
  specifies that the Boolean result be negated. The predicate reverses its return values, returning TRUE if the value is not NULL, and FALSE if the value is NULL.

### Return Type
[bool](other-simple-built-in-types-and-literals.md)

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  

**Dataset**   
```sql
@somePeople = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",    100, (int?)10000, new DateTime(2012,05,31), "cell:030-0074321,office:030-0076545"),
        (2, "Sophia",  100, (int?)15000, new DateTime(2012,03,19), "cell:(5) 555-4729,office:(5) 555-3745"),
        (3, "Liam",    100, (int?)30000, new DateTime(2014,09,14), ""),
        (6, "Emma",    200, (int?)8000,  new DateTime(2014,03,08), (string)null),
        (7, "Jacob",   200, (int?)8000,  new DateTime(2014,09,02), "cell:(5) 555-3932"),
        (8, "Olivia",  200, (int?)8000,  new DateTime(2013,12,11), "cell:88.60.15.31,office:88.60.15.32"),
        (10, "",       400, (int?)15000, new DateTime(2014,09,14), "cell:91.24.45.40,office:91.24.45.41"),
        (11, "Ethan ", 400, (int?)null,  new DateTime(2015,08,22), "cell:(604) 555-4729,office:(604) 555-3745")
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate, PhoneNumbers);
 ```

**IS NULL**   
```sql 
@result = 
    SELECT * FROM @somePeople 
    WHERE Salary IS NULL;

OUTPUT @result 
TO "/Output/ReferenceGuide/Predicates/IsNull.txt" 
USING Outputters.Tsv();
```

**IS NOT NULL**  
```sql
@result = 
    SELECT * FROM @somePeople
    WHERE Salary IS NOT NULL;

OUTPUT @result 
TO "/Output/ReferenceGuide/Predicates/IsNotNull.txt" 
USING Outputters.Tsv();
```

### See Also
* [LIKE, NOT LIKE (U-SQL)](like-not-like-u-sql.md)
* [NOT (U-SQL)](not-u-sql.md)
* [Operators (U-SQL)](operators-u-sql.md)
* [Logical Operators (U-SQL)](logical-operators-u-sql.md)
* [Comparison Operators (U-SQL)](comparison-operators-u-sql.md)




















