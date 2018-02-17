---
title: "ANTISEMIJOIN (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 57da496d-7a74-4a23-8c14-9636f4a20b6c
caps.latest.revision: 15
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# ANTISEMIJOIN (U-SQL)
Anti-Semijoins are U-SQL’s way filter a rowset based on the absence of its rows in another rowset. Other SQL dialects express this with the `SELECT * FROM A WHERE A.key NOT IN (SELECT B.key FROM B)` pattern. There are two variants: **`LEFT ANTISEMIJOIN`** and **`RIGHT ANTISEMIJOIN`**.  
  
A `LEFT ANTISEMIJOIN` (or just `ANTISEMIJOIN`) gives only those rows in the left rowset that have no matching row in the right rowset.  
  
The `RIGHT ANTISEMIJOIN` gives only those rows in the right rowset that have no matching row in the left rowset.  
  
The join expression in the ON clause specifies how to determine the match.  
  
### Example  
Given the following rowsets:  
  
| **EmpName** |   **DepID**        |  
|------------|-----------|  
| Rafferty   | 31        |  
| Jones      | 33        |  
| Heisenberg | 33        |  
| Robinson   | 34        |  
| Smith      | 34        |  
| Williams   | *null*    |  
  
| **DeptID** |     **DepName**        |  
|--------------|-------------|  
| 31           | Sales       |  
| 33           | Engineering |  
| 34           | Clerical    |  
| 35           | Marketing   |  
  
The following query finds all employees that are not in a valid department by finding all the employees in the left @employees rowset that do not have a depID that is listed in the right @departments rowset):  
  
```sql  
@employees = SELECT *  
               FROM (VALUES   
                      ("Rafferty", (int?) 31)  
                    , ("Jones", (int?) 33)  
                    , ("Heisenberg", (int?) 33)  
                    , ("Robinson", (int?) 34)  
                    , ("Smith", (int?) 34)  
                    , ("Williams", (int?) null)) AS E(EmpName, DepID);  
                      
@departments = SELECT *  
                FROM (VALUES  
                       ((int) 31, "Sales")  
                     , ((int) 33, "Engineering")  
                     , ((int) 34, "Clerical")  
                     , ((int) 35, "Marketing")) AS D(DepID, DepName);  
                       
@emps_notin_valid_dept =  
    SELECT e.EmpName, e.DepID  
    FROM @employees AS e  
         LEFT ANTISEMIJOIN (SELECT (int?) DepID AS DepID, DepName FROM @departments) AS d  
         ON e.DepID == d.DepID;  
  
  
OUTPUT @emps_notin_valid_dept   
TO "/output/rsLeftAntiSemiJoinEmployeesNotInValidDept.csv"  
USING Outputters.Csv();
```
  
The resulting rowset looks like:  
  
| **EmpName** |    **DepID**       |  
|---------------------------|-----------|  
| Williams                  | *null*    |  
  
The following query finds all departments without an employee:  
  
```sql  
@employees = SELECT *  
               FROM (VALUES   
                      ("Rafferty", (int?) 31)  
                    , ("Jones", (int?) 33)  
                    , ("Heisenberg", (int?) 33)  
                    , ("Robinson", (int?) 34)  
                    , ("Smith", (int?) 34)  
                    , ("Williams", (int?) null)) AS E(EmpName, DepID);  
                      
@departments = SELECT *  
                FROM (VALUES  
                       ((int) 31, "Sales")  
                     , ((int) 33, "Engineering")  
                     , ((int) 34, "Clerical")  
                     , ((int) 35, "Marketing")) AS D(DepID, DepName);  
                       
@depts_without_emps =  
    SELECT d.DepName, d.DepID  
    FROM @employees AS e  
         RIGHT ANTISEMIJOIN (SELECT (int?) DepID AS DepID, DepName FROM @departments) AS d   
         ON e.DepID == d.DepID;  
  
OUTPUT @depts_without_emps   
TO "/output/rsRightAntiSemiJoinDeptsWithoutEmployees.csv"  
USING Outputters.Csv();
```
  
Both queries return the same rowset:  
  
| **DepName** |    **DepID**       |  
|---------------------------------------------------|-----------|  
| Marketing                                         | 35        |  
  
**Additional Example**  
An example of comparing ANTISEMIJOIN against a subquery with NOT IN is available at [Subqueries with IN/NOT IN and SEMIJOIN/ANTISEMIJOIN](common-sql-expressions-in-u-sql.md#subQuery).

  
### See Also 
* [U-SQL SELECT Selecting from Joins](u-sql-select-selecting-from-joins.md)  
* [SELECT Expression (U-SQL)](select-expression-u-sql.md) 
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md)  
* [Data Modification Language (DML) Statements (U-SQL)](data-modification-language-dml-statements-u-sql.md)  
* [Output Statement (U-SQL)](output-statement-u-sql.md)
* [U-SQL Primary Rowset Expressions](query-statements-and-expressions-u-sql.md#pri_row_exp)  






