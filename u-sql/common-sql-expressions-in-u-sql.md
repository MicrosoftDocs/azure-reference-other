---
title: "Common SQL Expressions in U-SQL | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-11"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
keywords: 
  - "CASE"
  - "NULLIF"
  - "COALESCE"
  - "ISNULL"
  - "TOP"
  - "U-SQL"
  - "Subquery"
helpviewer_keywords: 
  - "CASE"
  - "NULLIF"
  - "COALESCE"
  - "ISNULL"
  - "TOP"
  - "U-SQL"
ms.assetid: 908fe956-2b83-4f32-a8db-e4595f52c5fc
caps.latest.revision: 24
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Common SQL Expressions in U-SQL
While U-SQL is based on SQL and provides many of the common SQL rowset expressions, it does not provide all of them and it is not ANSI SQL.   
  
For starters, its keywords such as SELECT have to be in UPPERCASE. And its expression language inside SELECT clauses, WHERE predicates etc is C#. This for example means, that the comparison operations inside a predicate follow C# syntax (e.g., a == "foo"), and that the language uses C# null semantics which is 2-valued and not 3-valued as in ANSI SQL. To help SQL users to get familiar with U-SQL, this section provides the mapping of some common SQL expressions and how to express them in U-SQL.  
  
### Examples    
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://channel9.msdn.com/Series/AzureDataLake/USQL-LocalRun).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

|Examples in this topic|
|---|
|&emsp;&#9679;&emsp;[CASE (Transact-SQL) and ?:](#case)<br />&emsp;&#9679;&emsp;[NULLIF (Transact-SQL) and ?:](#nullif)<br />&emsp;&#9679;&emsp;[COALESCE (Transact-SQL) and ??](#coalesce)<br />&emsp;&#9679;&emsp;[ISNULL (Transact-SQL) and ??](#isnull)<br />&emsp;&#9679;&emsp;[TOP (Transact-SQL) and FETCH](#top)<br />&emsp;&#9679;&emsp;[Subqueries with IN/NOT IN and SEMIJOIN/ANTISEMIJOIN](#subQuery)<p>                                                                                                                                                                                                      </p>|
  
 
<a name="case">**CASE (Transact-SQL) and ?:**</a>    
Consider using the conditional operator [`?:`](https://msdn.microsoft.com/library/ty67wk28.aspx) for situations where you would use [CASE (Transact-SQL)](https://msdn.microsoft.com/library/ms181765.aspx) in SQL.  See also, [Using `?:`](https://msdn.microsoft.com/library/azure/mt621341.aspx#condl).
```
@employees = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",   100, (int?)10000, new DateTime(2012,05,31)),
        (2, "Sophia", 100, (int?)15000, new DateTime(2012,03,19)),
        (3, "Liam",   100, (int?)30000, new DateTime(2014,09,14)),
        (4, "Amy",    100, (int?)35000, new DateTime(1999,02,27)),
        (5, "Justin", 600, (int?)15000, new DateTime(2015,01,12)),
        (6, "Emma",   200, (int?)8000,  new DateTime(2014,03,08)),
        (7, "Jacob",  200, (int?)8000,  new DateTime(2014,09,02)),
        (8, "Olivia", 200, (int?)8000,  new DateTime(2013,12,11)),
        (9, "Mason",  300, (int?)50000, new DateTime(2016,01,01)),
        (10, "Ava",   400, (int?)15000, new DateTime(2014,09,14))
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate);

/* T-SQL; Using CASE
SELECT  EmpID,
        EmpName,
		CASE DeptID
			WHEN 100 THEN 'Engineering'
            WHEN 200 THEN 'HR'
            WHEN 300 THEN 'Executive'
            WHEN 400 THEN 'Marketing'
            WHEN 500 THEN 'Sales'
			ELSE 'I did not anticipate this' 
		END AS Department,
        Salary,
        StartDate
FROM @employees;
*/

// U-SQL; Using ?: 
@result =
    SELECT  EmpID,
            EmpName,
            (DeptID == 100) ? "Engineering" : 
                (DeptID == 200) ? "HR" :
                (DeptID == 300) ? "Executive" :
                (DeptID == 400) ? "Marketing" :
                (DeptID == 500) ? "Sales" : "I did not anticipate this" AS Department,
            Salary,
            StartDate
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/CommonSQLExpressions/Case.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="nullif">**NULLIF (Transact-SQL) and ?:**</a>    
Consider using the conditional operator [`?:`](https://msdn.microsoft.com/library/ty67wk28.aspx) for situations where you would use [NULLIF (Transact-SQL)](https://msdn.microsoft.com/library/ms177562.aspx) in SQL. See also, [Using `?:`](https://msdn.microsoft.com/library/azure/mt621341.aspx#condl).
```
@dailySales = 
    SELECT * FROM 
        ( VALUES
        (62013, 22234, (int?)2398, 0),
        (62014, 25979, (int?)null, 0),
        (62015, 20437, (int?)0,    0),
        (62016, 20145, (int?)1184, 0),
        (62017, 12807, (int?)539,  539)
        ) AS T(SalesOrderID, CustomerID, SaleAmount, DisputedAmount);

/* T-SQL; Using NULLIF
SELECT  SalesOrderID, CustomerID, SaleAmount,
		NULLIF(SaleAmount, 0) AS SaleAmount2,
		NULLIF(SaleAmount, DisputedAmount) AS SaleAmount3
FROM @dailySales
*/
    
// U-SQL; Using ?:     
@result =
    SELECT  
            SalesOrderID, CustomerID, SaleAmount,

            // comparing to static value; returns null when SaleAmount equals 0, else SaleAmount
            (SaleAmount == 0 ? (int?)null : SaleAmount) AS SaleAmount2,

            // comparing to another column, returns null when SaleAmount equals DisputedAmount, else SaleAmount
            (SaleAmount == DisputedAmount ? (int?)null : SaleAmount) AS SaleAmount3  
    FROM @dailySales;

OUTPUT @result
TO "/Output/ReferenceGuide/CommonSQLExpressions/NullIf.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="coalesce">**COALESCE (Transact-SQL) and ??**</a>     
Consider using the null-coalescing operator [`??`](https://msdn.microsoft.com/library/ms173224.aspx) for situations where you would use [COALESCE (Transact-SQL)](https://msdn.microsoft.com/library/ms190349.aspx) in SQL.  See also, [Using `??`](https://msdn.microsoft.com/library/azure/mt621341.aspx#nullCoal)
```
@employees = 
    SELECT * FROM 
        ( VALUES
        (2, "Sophia",  100, (int?)15000, (int?)1000,  new DateTime(2012,03,19)),
        (9, "Mason",   300, (int?)50000, (int?)null,  new DateTime(2016,01,01)),
        (11, "Ethan",  400, (int?)null,  (int?)2000,  new DateTime(2015,08,22)),
        (12, "David",  800, (int?)null,  (int?)null,  new DateTime(2016,11,01)),
        (13, "Andrew", 100, (int?)null,  (int?)4000,  new DateTime(1995,07,16))
        ) AS T(EmpID, EmpName, DeptID, Salary, Bonus, StartDate);

/* T-SQL, Using COALESCE
SELECT  EmpName, Salary, Bonus, DeptID,
        COALESCE(Salary, 0) AS SalaryOrZero,
        COALESCE(Salary, Bonus) AS SalaryOrBonus,
		COALESCE(Salary, Bonus, DeptID) AS SalaryOrBonusOrDeptID,
        Salary,
        StartDate
FROM @employees;
*/

// U-SQL, Using ?? Operator
@result =
    SELECT  EmpName, Salary, Bonus, DeptID,
            Salary ?? 0 AS SalaryOrZero,
            Salary ?? Bonus AS SalaryOrBonus,
            Salary ?? Bonus ?? DeptID AS SalaryOrBonusOrDeptID,
            StartDate
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/CommonSQLExpressions/Coalesce.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="isnull">**ISNULL (Transact-SQL) and ??**</a>    
Consider using the null-coalescing operator [`??`](https://msdn.microsoft.com/library/ms173224.aspx) for situations where you would use [ISNULL (Transact-SQL)](https://msdn.microsoft.com/library/ms184325.aspx) in SQL.  Depending on your objective, for strings, also consider [IsNullOrEmpty](https://msdn.microsoft.com/library/system.string.isnullorempty(v=vs.110).aspx) and [IsNullOrWhiteSpace](https://msdn.microsoft.com/library/system.string.isnullorwhitespace(v=vs.110).aspx).
```
@employees = 
    SELECT * FROM 
        ( VALUES
        (2,  "Sophia",       (int?)15000),
        (11, (string)null,   (int?)null),
        (13, "",             (int?)0),
        (22, " ",            (int?)22000)
        ) AS T(EmpID, EmpName, Salary);

/* T-SQL, Using ISNULL
SELECT  EmpID, EmpName, Salary,
		ISNULL(Salary, 0) AS Salary2,
		ISNULL(EmpName, 'Unknown') AS EmpName2,
		ISNULL(NULLIF(EmpName, ''), 'Still Unknown') AS EmpName3
FROM @employees
*/

// U-SQL, Using ?? Operator
@result =
    SELECT  EmpID, EmpName, Salary,
            Salary ?? 0 AS Salary2,
            EmpName ?? "Unknown" AS EmpName2,

            // Alternatives
            (Equals(Salary, null)) ? 1 : Salary AS Salary3,
            (Salary == (int?)null) ? 2 : Salary AS Salary4,

            // String Alternatives
            string.IsNullOrEmpty(EmpName) ? "Still Unknown" : EmpName AS EmpName3,
            string.IsNullOrWhiteSpace(EmpName) ? "Really Unknown" : EmpName AS EmpName4
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/CommonSQLExpressions/IsNull.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="top">**TOP (Transact-SQL) and FETCH**</a>    
[TOP (Transact-SQL)](https://msdn.microsoft.com/library/ms189463.aspx) returns the first N number of rows in an undefined order or a defined order when combined with ORDER BY. In U-SQL, [FETCH](../u-sql/output-statement-u-sql.md#OBOFC) can be used to return the first N number of rows only in a defined order; the ORDER BY clause must be used.  Consider the use of [SAMPLE](../u-sql/sample-u-sql.md) if a defined order is not desired or required.  See also, [ROW_NUMBER](../u-sql/row-number-u-sql.md).
```
@employees = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",   100, (int?)10000, new DateTime(2012,05,31)),
        (2, "Sophia", 100, (int?)15000, new DateTime(2012,03,19)),
        (3, "Liam",   100, (int?)30000, new DateTime(2014,09,14)),
        (4, "Amy",    100, (int?)35000, new DateTime(1999,02,27)),
        (5, "Justin", 600, (int?)15000, new DateTime(2015,01,12)),
        (6, "Emma",   200, (int?)8000,  new DateTime(2014,03,08)),
        (7, "Jacob",  200, (int?)8000,  new DateTime(2014,09,02)),
        (8, "Olivia", 200, (int?)8000,  new DateTime(2013,12,11)),
        (9, "Mason",  300, (int?)50000, new DateTime(2016,01,01)),
        (10, "Ava",   400, (int?)15000, new DateTime(2014,09,14))
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate);

/* T-SQL, Using TOP
SELECT TOP(5) *
FROM @employees
-- ORDER BY EmpId -- Optional in T-SQL
*/

// U-SQL, Using FETCH
OUTPUT @employees
TO "/Output/ReferenceGuide/CommonSQLExpressions/Top1.csv"
ORDER BY EmpID FETCH 5 ROWS
USING Outputters.Csv(outputHeader: true);


// U-SQL, Using SAMPLE
@result =
    SELECT EmpID, EmpName
    FROM @employees
    SAMPLE ANY(5);

OUTPUT @result
TO "/Output/ReferenceGuide/CommonSQLExpressions/Top2.csv"
USING Outputters.Csv(outputHeader: true);


// U-SQL, Using ROW_NUMBER
@result =
    SELECT ROW_NUMBER() OVER (ORDER BY Salary DESC) AS row,
           *
    FROM @employees;

@result =
    SELECT *
    FROM @result
    WHERE row <= 5;

OUTPUT @result
TO "/ReferenceGuide/CommonSQLExpressions/Top3.txt"
USING Outputters.Tsv(outputHeader: true);
```


<a name="subQuery">**Subqueries with IN/NOT IN and SEMIJOIN/ANTISEMIJOIN**</a>   
Consider using [SEMIJOIN (U-SQL)](../u-sql/semijoin-u-sql.md) for situations where you would use a subquery with IN in SQL.
Consider using [ANTISEMIJOIN (U-SQL)](../u-sql/antisemijoin-u-sql.md) for situations where you would use a subquery with NOT IN in SQL.
```
@employees = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",   100, (int?)10000, new DateTime(2012,05,31)),
        (2, "Sophia", 100, (int?)15000, new DateTime(2012,03,19)),
        (3, "Liam",   100, (int?)30000, new DateTime(2014,09,14)),
        (4, "Amy",    100, (int?)35000, new DateTime(1999,02,27)),
        (5, "Justin", 600, (int?)15000, new DateTime(2015,01,12)),
        (6, "Emma",   200, (int?)8000,  new DateTime(2014,03,08)),
        (7, "Jacob",  200, (int?)8000,  new DateTime(2014,09,02)),
        (8, "Olivia", 200, (int?)8000,  new DateTime(2013,12,11)),
        (9, "Mason",  300, (int?)50000, new DateTime(2016,01,01)),
        (10, "Ava",   400, (int?)15000, new DateTime(2014,09,14))
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate);
        
@departments = 
    SELECT * FROM 
        ( VALUES
        (100, "Engineering"),
        (200, "HR"),
        (300, "Executive"),
        (400, "Marketing"),
        (500, "Sales"),
        (600, "Clerical"),
        (800, "Reserved")
        ) AS T(DeptID, DeptName);

/* T-SQL; Using a subquery with IN
SELECT * 
FROM @employees
WHERE DeptID IN 
	(SELECT DeptID FROM @departments WHERE DeptName IN ('Engineering', 'Executive'));
*/

// U-SQL; Using SEMIJOIN 
@result =
    SELECT *
    FROM @employees AS e
    LEFT SEMIJOIN (SELECT DeptID FROM @departments WHERE DeptName IN ("Engineering", "Executive")) AS sc
    ON e.DeptID == sc.DeptID;

OUTPUT @result
TO "/Output/ReferenceGuide/Joins/SemiJoins/SubqueryIN.txt"
USING Outputters.Tsv(outputHeader: true);

/* T-SQL; Using a subquery with NOT IN
SELECT * 
FROM @employees
WHERE DeptID NOT IN 
	(SELECT DeptID FROM @departments WHERE DeptName IN ('Engineering', 'Executive'));
*/

// U-SQL; Using ANTISEMIJOIN 
@result =
    SELECT *
    FROM @employees AS e
    LEFT ANTISEMIJOIN (SELECT DeptID FROM @departments WHERE DeptName IN ("Engineering", "Executive")) AS sc
    ON e.DeptID == sc.DeptID;

OUTPUT @result
TO "/Output/ReferenceGuide/Joins/AntiSemiJoins/SubqueryNOTIN.txt"
USING Outputters.Tsv(outputHeader: true);

// BONUS: Switch "LEFT" to "RIGHT" in the above examples and observe the results.
``` 
  
### See also   
* [PIVOT and UNPIVOT (U-SQL)](../u-sql/pivot-and-unpivot-u-sql.md)  
* [Built-in Functions (U-SQL)](../u-sql/built-in-functions-u-sql.md)    
* [ORDER BY and OFFSET/FETCH Clause (U-SQL)](../u-sql/order-by-and-offset-fetch-clause-u-sql.md)     
* [C# Functions and Operators (U-SQL)](../u-sql/csharp-functions-and-operators-u-sql.md)   


