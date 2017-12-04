---
title: "INNER JOIN (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: bb1d54fc-729f-4903-9474-4b9124c28ca6
caps.latest.revision: 13
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# INNER JOIN (U-SQL)
An inner join will combine the selected columns from the two joined rowsets for every combination of rows that satisfy the join comparison predicate.  
  
### Example  
Let’s assume the following rowsets are referenced by the respective rowset variables:  
  
| @employees |           |  
|------------|-----------|  
| **EmpName** string | **DepID** int? |  
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
  
Then the following inner join (the @departments.DepID has to be cast to (int?) since C# does not allow comparison of int with int?).  
  
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
                       
@rs_inner =   
    SELECT e.DepID AS EmpDepID, d.DepID, e.EmpName, d.DepName       
    FROM @employees AS e  
         INNER JOIN (SELECT (int?) DepID AS DepID, DepName FROM @departments) AS d   
         ON e.DepID == d.DepID;  
  
OUTPUT @rs_inner   
TO "/output/rsInnerJoin.csv"  
USING Outputters.Csv();  
```  
  
produces the following result. Note that it does not include employees that have no department nor does it include departments that have no employees.  
  
| @rs_inner |           |             |             |  
|------------|-----------|-------------|-------------|  
| **EmpDepID** int?  | **DepID** int? | **EmpName** string | **DepName** string |  
| 31         | 31        | Rafferty    | Sales       |  
| 33         | 33        | Jones       | Engineering |  
| 33         | 33        | Heisenberg  | Engineering |  
| 34         | 34        | Robinson    | Clerical    |  
| 34         | 34        | Smith       | Clerical    |  

### See Also 
* [U-SQL SELECT Selecting from Joins](u-sql-select-selecting-from-joins.md)  
* [SELECT Expression (U-SQL)](select-expression-u-sql.md) 
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md) 
* [Data Modification Language (DML) Statements (U-SQL)](data-modification-language-dml-statements-u-sql.md)  
* [Output Statement (U-SQL)](output-statement-u-sql.md)
* [U-SQL Primary Rowset Expressions](query-statements-and-expressions-u-sql.md#pri_row_exp)







