---
title: "CASE Expression (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2018-06-19"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# CASE Expression (U-SQL)
Evaluates a list of conditions and returns one of multiple possible result expressions.  The CASE expression has two formats:

 - The simple `CASE` expression compares an expression to a set of at least one simple expression to determine the result. 

 - The searched `CASE` expression evaluates a set of at least one Boolean expression to determine the result. 

Both formats support an `ELSE` clause that is optional if the result type is nullable and required if the result type is not nullable. 

The result of the `CASE` expression is the first match in lexical order or null if no match can be found.  The `CASE` expression can be used in any U-SQL expression or clause that allows a valid scalar expression, but cannot be used inside C# code blocks.


## Syntax
<pre>
CASE_Expression := 
    Simple_CASE_Expression | Searched_CASE_Expression.

Simple_CASE_Expression :=
    'CASE' <a href="#input_exp">input_expression</a> 
    'WHEN' <a href="#when_exp">when_expression</a> 'THEN' <a href="#result_exp">result_expression</a>
    { 'WHEN' <a href="#when_exp">when_expression</a> 'THEN' <a href="#result_exp">result_expression</a> }
    [ 'ELSE' <a href="#result_exp">result_expression</a> ]
    'END'.

Searched_CASE_Expression :=
    'CASE' 
    'WHEN' <a href="#bool_exp">boolean_expression</a> 'THEN' <a href="#result_exp">result_expression</a>
    { 'WHEN' <a href="#bool_exp">boolean_expression</a> 'THEN' <a href="#result_exp">result_expression</a> }
    [ 'ELSE' <a href="#result_exp">result_expression</a> ]
    'END'.
</pre>
<br />

## Semantics of Syntax Elements  
- <a name="input_exp"></a>**`input_expression`**  
The `input_expression` in the `Simple_CASE_Expression` specifies the U-SQL scalar expression that will be compared against the values specified in the `WHEN` clauses.

- <a name="when_exp"></a>**`when_expression`**  
The `when_expression` in the `Simple_CASE_Expression` specifies the U-SQL scalar expression that will be compared against the value specified by the `input_expression`. The first `when_expression` in lexical order that evaluates to true will trigger the execution of the `result_expression` in the associated `THEN` clause. All `when_expression`s in a `CASE` expression at the same nesting level must be of the same result type and be of the same type as the `input_expression` or a compilation error is raised.

- <a name="bool_exp"></a>**`boolean_expression`**  
The `boolean_expression` in the `Searched_CASE_Expression`'s  `WHEN` clause specifies a condition as a U-SQL Boolean expression. If the expression is not resulting in a Boolean data type, a compile time error is raised. The first  `WHEN` clause in lexical order for which the `boolean_expression`  evaluates to true will trigger the execution of the `result_expression` in the associated `THEN` clause. 

- <a name="result_exp"></a>**`result_expression`**  
The `result_expression` specifies the expression that will be the result of the `CASE` expression if the associated condition evaluates to true. All `result_expression`s in a `CASE` expression at the same nesting level must be of the same result type or a compilation error is raised.


## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.  
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  

**Dataset**  
```sql
@employees = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",   100, 10000, new DateTime(2012,05,31)),
        (2, "Sophia", 100, 15000, new DateTime(2012,03,19)),
        (3, "Liam",   100, 30000, new DateTime(2014,09,14)),
        (4, "Amy",    100, 35000, new DateTime(1999,02,27)),
        (5, "Justin", 600, 15000, new DateTime(2015,01,12)),
        (6, "Emma",   200, 8000,  new DateTime(2014,03,08)),
        (7, "Jacob",  200, 8000,  new DateTime(2014,09,02)),
        (8, "Olivia", 200, 8000,  new DateTime(2013,12,11)),
        (9, "Mason",  300, 50000, new DateTime(2016,01,01)),
        (10, "Ava",   400, 15000, new DateTime(2014,09,14))
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate);
```

**Simple CASE expression**   
```sql 
@result = 
    SELECT  EmpID,
            EmpName,
            CASE DeptID
                WHEN 100 THEN "Engineering"
                WHEN 200 THEN "HR"
                WHEN 300 THEN "Executive"
                WHEN 400 THEN "Marketing"
                WHEN 500 THEN "Sales"
                ELSE "I did not anticipate this"
            END AS Department,
            Salary,
            StartDate.ToShortDateString() AS StartDate
    FROM @employees;

OUTPUT @result
TO "/ReferenceGuide/QSE/CASE/simple.txt"
USING Outputters.Tsv(outputHeader: true);
``` 

**Searched CASE expression**
```sql
@result = 
    SELECT  EmpID,
            EmpName,
            DeptID,
            CASE 
                WHEN Salary < 10000 THEN "Tier 1"
                WHEN Salary >= 1000 AND Salary < 20000 THEN "Tier 2"
                WHEN Salary >= 30000 THEN "Tier 3"
                ELSE "I did not anticipate this"
            END AS SalaryTier,
            Salary,
            StartDate.ToShortDateString() AS StartDate
    FROM @employees;

OUTPUT @result
TO "/ReferenceGuide/QSE/CASE/searched.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Nested CASE**
```sql
@result =
    SELECT  EmpID,
            EmpName,
            DeptID,
		CASE 
            WHEN DeptID == 100 THEN 
			    CASE WHEN Salary <= 15000 THEN "E - Tier 1"
                     ELSE "E - Tier 2"
                END
            WHEN Salary < 10000 THEN "Tier 1"
            WHEN Salary >= 1000 AND Salary < 20000 THEN "Tier 2"
            WHEN Salary >= 30000 THEN "Tier 3"
            ELSE "I did not anticipate this"
        END AS SalaryTier,
        Salary,
        StartDate.ToShortDateString() AS StartDate
FROM @employees;

OUTPUT @result
TO "/ReferenceGuide/QSE/CASE/nested.txt"
USING Outputters.Tsv(outputHeader: true);


// nested alternative
@result =
    SELECT  EmpID,
            EmpName,
            DeptID,
		    CASE 
                WHEN DeptID == 100 AND Salary <= 15000 THEN "E - Tier 1"
                WHEN DeptID == 100 AND Salary < 15000 THEN "E - Tier 2"
                WHEN Salary < 10000 THEN "Tier 1"
                WHEN Salary >= 1000 AND Salary < 20000 THEN "Tier 2"
                WHEN Salary >= 30000 THEN "Tier 3"
                ELSE "I did not anticipate this"
            END AS SalaryTier,
            Salary,
            StartDate.ToShortDateString() AS StartDate
FROM @employees;

OUTPUT @result
TO "/ReferenceGuide/QSE/CASE/nested_alternative.txt"
USING Outputters.Tsv(outputHeader: true);
```

## See Also 
* [SELECT Expression (U-SQL)](select-expression-u-sql.md)
* [?: (Conditional)](csharp-functions-and-operators-u-sql.md#condl)
* [?? (Null-Coalescing)](csharp-functions-and-operators-u-sql.md#nullCoal)
