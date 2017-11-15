---
title: "PERCENTILE_CONT (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e9b0ec62-085f-43fe-b2ea-d97f90c8c390
caps.latest.revision: 13
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# PERCENTILE_CONT (U-SQL)
The PERCENTILE_CONT analytic function calculates a percentile based on a continuous distribution of the values in the window. The result is interpolated and might not be equal to any of the specific values in the column.  

PERCENTILE_CONT can only be used in the context of a [windowing expression](../u-sql/over-expression-u-sql.md). 

<table><th align="left">Syntax</th><tr><td><pre>
PERCENTILE_CONT_Expression :=                                                                            
     'PERCENTILE_CONT' '(' <a href="#dbl_lit">double_literal</a> ')'
     '<a href="#wg_soc">WITHIN' 'GROUP' '(' Simple_Order_By_Clause ')</a>'.
</pre></td></tr></table>
   
### Semantics of Syntax Elements 
* <a name="dbl_lit"></a>**`double_literal`**     
The percentile to compute. The value must range between 0.0 and 1.0 and be of type [double](../u-sql/numeric-types-and-literals.md). 

* <a name="wg_soc"></a>**`WITHIN GROUP ( Simple_Order_By_Clause )`**  
  Specifies a list of numeric values to sort and compute the percentile over.  

  <table><th>Syntax</th><tr><td><pre>
  Simple_Order_By_Clause :=                                                                           
       'ORDER' 'BY' Sort_Item_Expression.<br />
  Sort_Item_Expression :=     
       expression [Sort_Direction].<br />
  Sort_Direction :=
       'ASC' | 'DESC'.
  </pre></td></tr></table>

  Only one `ORDER BY` expression is allowed. The type of the expression has to be a nullable or nonnullable [numeric type](../u-sql/numeric-types-and-literals.md). The default sort order is ascending. 

### Return Type 
The return type is [double?](../u-sql/numeric-types-and-literals.md). 

### Usage in Windowing Expression 
This analytic function can be used in a [windowing expression](../u-sql/over-expression-u-sql.md) with the following restrictions: 
* Only the [PARTITION BY](../u-sql/over-expression-u-sql.md#OPBC) clause can be specified with the [OVER](../u-sql/over-expression-u-sql.md) operator. 
* The [ORDER BY](../u-sql/over-expression-u-sql.md#OBC) clause in the [OVER](../u-sql/over-expression-u-sql.md) operator is not allowed. 
* The [ROWS](../u-sql/over-expression-u-sql.md#row_cla) clause in the [OVER](../u-sql/over-expression-u-sql.md) operator is not allowed. 

### Example
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The example below is based on the dataset defined below.  Ensure your execution includes the rowset variable.
```
@employees = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",   "Engineering", 100, 10000),
        (2, "Sophia", "Engineering", 100, 20000),
        (3, "Liam",   "Engineering", 100, 30000),
        (4, "Amy",    "Engineering", 100, 35000),
        (5, "Emma",   "HR",          200, 8000),
        (6, "Jacob",  "HR",          200, 8000),
        (7, "Olivia", "HR",          200, 8000),
        (8, "Mason",  "Executive",   300, 50000),
        (9, "Ava",    "Marketing",   400, 15000),
        (10, "Ethan", "Marketing",   400, 9000) 
        ) AS T(EmpID, EmpName, DeptName, DeptID, Salary);
```

**Using PERCENTILE_CONT**   
The following example uses `PERCENTILE_CONT` to find the median employee salary in each department.
```
@result =
    SELECT DISTINCT DeptName,
                    PERCENTILE_CONT(0.5) WITHIN GROUP(ORDER BY Salary) OVER(PARTITION BY DeptName) AS MedianCont
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/percentile_cont/example.csv"
USING Outputters.Csv();
```

### See Also 
* [PERCENTILE_DISC (U-SQL)](../u-sql/percentile-disc-u-sql.md)
* [Analytic Functions (U-SQL)](../u-sql/analytic-functions-u-sql.md)  
* [OVER Expression (U-SQL)](../u-sql/over-expression-u-sql.md) 
