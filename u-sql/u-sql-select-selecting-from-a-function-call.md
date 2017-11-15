---
title: "U-SQL SELECT Selecting from a Function Call | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: efb9774b-37b6-4156-92d6-3586c0da8410
caps.latest.revision: 15
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL SELECT Selecting from a Function Call
U-SQL allows selecting from a table-valued function (TVF). Note that U-SQL Table-valued functions – unlike their T-SQL cousins – are always inlined where they are called.  
  
The following syntax shows the FROM clause for just the selection from a TVF.   
  
<table><th align="left">Syntax</th><tr><td><pre>
Select_From_TVF_Clause :=                                                                                
     'FROM' <a href="#fun_cal">Function_Call</a> 'AS' <a href="#QUI">Quoted_or_Unquoted_Identifier</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements    
-   <a name="fun_cal"></a>**`Function_Call`**   
    The table-valued function is called as outlined [here](../USQL/table-valued-function-expression-u-sql.md) in the [FROM](../USQL/from-clause-u-sql.md) clause of a SELECT expression. The function call will provide values to its parameters positionally, or the keyword DEFAULT to indicate that the default value of the argument (if defined) should be chosen.  
  
    The content of the function will be inlined in the script conceptually similarly to the following rewrite (although the query processor will probably perform more rewrites during algebrization and optimization of the query):  
  
    If the table-valued function TVF is defined as:  
  
    ```
    CREATE FUNCTION TVF() RETURNS @r TABLE(I int) AS  
    BEGIN  
      @v = SELECT * FROM (VALUES(1),(2),(3)) AS V(I);  
      @r = SELECT I+1 AS I FROM @v;  
    END;
    ```
  
    It will be inlined in the following query:  
  
    ```
    @x = SELECT * FROM TVF() AS T;
    ```
      
    And the query is then conceptually rewritten to  
  
    ```
    @v = SELECT * FROM (VALUES(1),(2),(3)) AS V(I);  
    @r = SELECT I+1 AS I FROM @v;  
    @x = SELECT * FROM @r AS T;
    ```
      
    It does preserve the function scoping rules though.  
  
-   **`'AS'`** <a name="QUI"></a>**`Quoted_or_Unquoted_Identifier`**  
    When invoking a table-valued function in a SELECT’s FROM clause, a rowset alias has to be provided.  
  
### Example
- The example is designed for execution in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed locally.  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The example below is based on the data and objects below defined below.
```
CREATE DATABASE IF NOT EXISTS TestReferenceDB;
USE DATABASE TestReferenceDB; 

DROP TABLE IF EXISTS dbo.Employees;
CREATE TABLE dbo.Employees
(
    EmpID int,
    EmpName string,
    DeptID int,
    Salary int?,
    StartDate DateTime,
    INDEX clx_EmpID CLUSTERED(EmpID ASC) PARTITIONED BY HASH(EmpID)
);

INSERT INTO dbo.Employees
VALUES
(1, "Noah",   100, (int?)10000, new DateTime(2012,05,31)),
(2, "Sophia", 100, (int?)15000, new DateTime(2012,03,19)),
(3, "Liam",   100, (int?)30000, new DateTime(2014,09,14)),
(4, "Amy",    100, (int?)35000, new DateTime(1999,02,27)),
(5, "Justin", 100, (int?)15000, new DateTime(2015,01,12)),
(6, "Emma",   200, (int?)8000,  new DateTime(2014,03,08)),
(7, "Jacob",  200, (int?)8000,  new DateTime(2014,09,02)),
(8, "Olivia", 200, (int?)8000,  new DateTime(2013,12,11)),
(9, "Mason",  300, (int?)50000, new DateTime(2016,01,01)),
(10, "Ava",   400, (int?)15000, new DateTime(2014,09,14)),
(11, "Ethan", 400, (int?)9000,  new DateTime(2015,08,22)),
(12, "David", 800, (int?)100,   new DateTime(2016,11,01)),
(13, "Andrew", 100, (int?)null, new DateTime(1995,07,16)); // Create a NULL Salary

// Create function
DROP FUNCTION IF EXISTS TestReferenceDB.dbo.DeptEmployees;
CREATE FUNCTION TestReferenceDB.dbo.DeptEmployees(@deptID int)
RETURNS @tvf_result
AS
BEGIN
    @tvf_result =
        SELECT *
        FROM TestReferenceDB.dbo.Employees
        WHERE DeptID == @deptID;
END;
```

**Basic Call**   
The query below calls the function `DeptEmployees` and passes `100` for `DeptID`.  The function returns all employees for the given `DeptID`.
```
// Execute function
@result =
    SELECT *
    FROM TestReferenceDB.dbo.DeptEmployees(100) AS DeptEmployees;

// Output results
OUTPUT @result   
TO "/Output/ReferenceGuide/StatementsAndExpressions/TVFcall/example.csv"
USING Outputters.Csv();
```
  
### See Also 
* [Query Statements and Expressions (U-SQL)](../USQL/query-statements-and-expressions-u-sql.md) 
* [Data Modification Language (DML) Statements (U-SQL)](../USQL/data-modification-language-dml-statements-u-sql.md)   
* [Output Statement (U-SQL)](../USQL/output-statement-u-sql.md)  

