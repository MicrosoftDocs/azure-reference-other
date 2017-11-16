---
title: "CROSS JOIN (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 017959df-5dd8-4856-b382-5d4853800c80
caps.latest.revision: 15
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CROSS JOIN (U-SQL)
A cross join returns the Cartesian product of rows from the rowsets in the join. In other words, it will combine each row from the first rowset with each row from the second rowset.  
  
Note that this is potentially an expensive and dangerous operation since it can lead to a large data explosion. It is best used in scenarios where a normal join cannot be used and very selective predicates are being used in the WHERE clause to limit the number of produced rows.  
  
### Examples    
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


**Basic Example**  
Using the input rowsets  
  
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
| **DeptID** int  | **DepName** string |  
| 31           | Sales       |  
| 33           | Engineering |  
| 34           | Clerical    |  
| 35           | Marketing   |  
  
the following cross join  
  
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
                       
@rs_cross =   
    SELECT e.EmpName, d.DepName  
    FROM @employees AS e   
         CROSS JOIN @departments AS d  
    WHERE d.DepName == "Engineering";  
  
OUTPUT @rs_cross   
TO "/Output/ReferenceGuide/Joins/CrossJoins/ExampleA.csv"
USING Outputters.Csv();  
```  
  
produces this rowset  
  
| @rs_cross |             |  
|------------|-------------|  
| **EmpName** string    | **DepName** string |  
| Rafferty   | Engineering |  
| Jones      | Engineering |  
| Heisenberg | Engineering |  
| Robinson   | Engineering |  
| Smith      | Engineering |  
| Williams   | Engineering |  
  
Note that without the filter on the DepName, the resulting rowset would have produced 6x4=24 rows.  

**Additional Examples**  
```
@right = 
    SELECT * FROM 
        ( VALUES
        (0, 99, "Ford Motor Company", "Ford"),
        (100, 199, "Ford Motor Company", "Lincoln"),
        (200, 299, "Ford Motor Company", "Motorcraft"),
        (300, 399, "General Motors Company", "Buick"),
        (400, 499, "General Motors Company", "Chevrolet"),
        (500, 599, "General Motors Company", "Cadillac"),
        (600, 699, "General Motors Company", "GMC"),
        (700, 799, "Fiat Chrysler", "Chrysler"),
        (800, 899, "Fiat Chrysler", "Dodge"),
        (900, 999, "Fiat Chrysler", "Jeep"),
        (1000, 1099, "Fiat Chrysler", "Ram"),
        (1100, 1199, "Fiat Chrysler", "Mopar"),
        (1200, 1299, "Fiat Chrysler", "SRT")
        ) AS T(carIDstart, carIDend, Automaker, Division);

@left = 
    SELECT * FROM 
        ( VALUES
        (3, "Mustang", "1964"),
        (7, "Fiesta", "1976"),
        (133, "Navigator", "1998"),
        (160, "Continental", "2017"),
        (639, "Canyon", "2004"),
        (801, "Challenger", "2008"),
        (802, "Charger", "2006")
        ) AS T(carID, currentModel, introYear);

@result = 
    SELECT  l.currentModel,
            r.Division,
            l.introYear
    FROM    @left AS l
    CROSS JOIN    @right AS r
    WHERE   l.carID BETWEEN r.carIDstart AND r.carIDend;

OUTPUT @result
TO "/Output/ReferenceGuide/Joins/CrossJoins/ExampleB.csv"
USING Outputters.Csv(outputHeader: true);
```

* [Table type in a procedure as a returned value](create-type-u-sql.md#sproc_pass) (a cross join is used in the procedure definition)

### See Also 
* [U-SQL SELECT Selecting from Joins](u-sql-select-selecting-from-joins.md)  
* [SELECT Expression (U-SQL)](select-expression-u-sql.md)
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md)  
* [Data Modification Language (DML) Statements (U-SQL)](data-modification-language-dml-statements-u-sql.md)    
* [Output Statement (U-SQL)](output-statement-u-sql.md)
* [U-SQL Primary Rowset Expressions](query-statements-and-expressions-u-sql.md#pri_row_exp) 






