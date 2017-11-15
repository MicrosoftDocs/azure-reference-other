---
title: "ANTISEMIJOIN (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
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
  
| @employees |           |  
|------------|-----------|  
| **EmpName** string    | **DepID** int? |  
| Rafferty   | 31        |  
| Jones      | 33        |  
| Heisenberg | 33        |  
| Robinson   | 34        |  
| Smith      | 34        |  
| Williams   | *null*    |  
  
| @departments |             |  
|--------------|-------------|  
| **DeptID** int | **DepName** string |  
| 31           | Sales       |  
| 33           | Engineering |  
| 34           | Clerical    |  
| 35           | Marketing   |  
  
The following query finds all employees that are not in a valid department by finding all the employees in the left @employees rowset that do not have a depID that is listed in the right @departments rowset):  
  
```  
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
  
| @emps_notin_valid_dept |           |  
|---------------------------|-----------|  
| **EmpName** string        | **DepID** int? |  
| Williams                  | *null*    |  
  
The following query finds all departments without an employee:  
  
```  
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
  
| @depts_without_emps_0/@depts_without_emps_1 |           |  
|---------------------------------------------------|-----------|  
| **DepName** string                                | **DepID** int? |  
| Marketing                                         | 35        |  
  
**Additional Example**  
An example of comparing ANTISEMIJOIN against a subquery with NOT IN is available at [Subqueries with IN/NOT IN and SEMIJOIN/ANTISEMIJOIN](../u-sql/common-sql-expressions-in-u-sql.md#subQuery).

  
### See Also 
* [U-SQL SELECT Selecting from Joins](../u-sql/u-sql-select-selecting-from-joins.md)  
* [SELECT Expression (U-SQL)](../u-sql/select-expression-u-sql.md) 
* [Query Statements and Expressions (U-SQL)](../u-sql/query-statements-and-expressions-u-sql.md)  
* [Data Modification Language (DML) Statements (U-SQL)](../u-sql/data-modification-language-dml-statements-u-sql.md)  
* [Output Statement (U-SQL)](../u-sql/output-statement-u-sql.md)
* [U-SQL Primary Rowset Expressions](../u-sql/query-statements-and-expressions-u-sql.md#pri_row_exp)  






