---
title: "OUTER JOIN (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 141c609f-03b2-4135-9e21-a429d1777b1f
caps.latest.revision: 12
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# OUTER JOIN (U-SQL)
An outer join will combine the selected columns from the two joined rowsets for every combination of rows that satisfy the join predicate and will add the rows that are not having a match for the specified join side.  
  
If `LEFT` is specified (or just `OUTER JOIN`) then all rows from the left side rowset will be selected and for any rows that have no match in the right rowset, the right rowset columns will receive a `null` value.  
  
### Examples
**A.  LEFT OUTER JOIN**    
Using the input rowsets  
  
| @employees |           |  
|------------|-----------|  
| **EmpName** string  | **DepID** int? |  
| Rafferty   | 31        |  
| Jones      | 33        |  
| Heisenberg | 33        |  
| Robinson   | 34        |  
| Smith      | 34        |  
| Williams   | *null*    |  
  
| @departments |             |  
|--------------|-------------|  
| **DeptID** int  | **DepName** string |  
| 31           | Sales       |  
| 33           | Engineering |  
| 34           | Clerical    |  
| 35           | Marketing   |  
  
the following left outer join  
  
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
                       
@rs_leftouter =   
    SELECT e.EmpName, d.DepName  
    FROM @employees AS e   
         LEFT OUTER JOIN (SELECT (int?) DepID AS DepID, DepName FROM @departments) AS d  
         ON e.DepID == d.DepID;  
  
OUTPUT @rs_leftouter   
TO "/output/rsLeftOuterJoin.csv"  
USING Outputters.Csv();  
```  
  
produces this rowset  
  
| @rs_leftouter |             |  
|----------------|-------------|  
| **EmpName** string | **DepName** string |  
| Rafferty       | Sales       |  
| Jones          | Engineering |  
| Heisenberg     | Engineering |  
| Robinson       | Clerical    |  
| Smith          | Clerical    |  
| Williams       | *null*      |  
  
Since the employee with the name Williams did not have an assigned department, its row receives a `null` in the DepName column.  
  
If `RIGHT` is specified then all rows from the right side rowset will be selected and for any rows that have no match in the left rowset, the left rowset columns will receive a `null` value.  
  
**B.  RIGHT OUTER JOIN**    
Using the same input rowsets as above, the following right outer join  
  
```  
@rs_rightouter =   
    SELECT e.EmpName, d.DepName  
    FROM @employees AS e   
         RIGHT OUTER JOIN (SELECT (int?) DepID AS DepID, DepName FROM @departments) AS d  
         ON e.DepID == d.DepID;  
```  
  
produces this rowset  
  
| @rs_rightouter |             |  
|-----------------|-------------|  
| **EmpName** string | **DepName** string |  
| Rafferty        | Sales       |  
| Heisenberg      | Engineering |  
| Jones           | Engineering |  
| Smith           | Clerical    |  
| Robinson        | Clerical    |  
| *null*          | Marketing   |  
  
Since the Marketing department did not have any assigned employees, its row receives a `null` in the EmpName column.  
  
If `FULL` is specified then all rows from both the left and right side rowsets will be selected and for any rows where their match on the other side is missing, the “missing” columns will receive a `null` value.  
  
**C.  FULL OUTER JOIN**    
Using the same input rowsets as above, the following full outer join  
  
```  
@rs_fullouter =   
    SELECT e.EmpName, d.DepName  
    FROM @employees AS e   
         FULL OUTER JOIN (SELECT (int?) DepID AS DepID, DepName FROM @departments) AS d  
         ON e.DepID == d.DepID;  
```  
  
produces this rowset  
  
| @rs_fullouter |             |  
|----------------|-------------|  
| **EmpName** string | **DepName** string |  
| Rafferty       | Sales       |  
| Jones          | Engineering |  
| Heisenberg     | Engineering |  
| Robinson       | Clerical    |  
| Smith          | Clerical    |  
| *null*         | Marketing   |  
| Williams       | *null*      |  
  
In this case both rows that are missing a match are added with null values.  

### See Also 
* [U-SQL SELECT Selecting from Joins](../u-sql/u-sql-select-selecting-from-joins.md)  
* [SELECT Expression (U-SQL)](../u-sql/select-expression-u-sql.md) 
* [Query Statements and Expressions (U-SQL)](../u-sql/query-statements-and-expressions-u-sql.md) 
* [Data Modification Language (DML) Statements (U-SQL)](../u-sql/data-modification-language-dml-statements-u-sql.md)    
* [Output Statement (U-SQL)](../u-sql/output-statement-u-sql.md)
* [U-SQL Primary Rowset Expressions](../u-sql/query-statements-and-expressions-u-sql.md#pri_row_exp) 





