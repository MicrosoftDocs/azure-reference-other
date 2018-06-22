---
title: "PERCENTILE_DISC (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 0c589e5b-6643-46b9-8194-63a70f493bb2
caps.latest.revision: 11
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# PERCENTILE_DISC (U-SQL)
The `PERCENTILE_DISC` analytic function computes a specific percentile for sorted values in the specified window based on a discrete distribution of the column values. The result is equal to a specific value in the column. 

For a given percentile value `P`, `PERCENTILE_DISC` returns the value with the smallest [CUME_DIST](cume-dist-u-sql.md) value for the same sorted list of values that is greater than or equal to `P`.  

For example, `PERCENTILE_DISC(0.5)` will compute the 50th percentile (that is, the median) of an expression.  

`PERCENTILE_DISC` can only be used in the context of a [windowing expression](over-expression-u-sql.md). 

## Syntax
<pre>
PERCENTILE_DISC_Expression := 
    'PERCENTILE_DISC' '(' <a href="#dbl_lit">double_literal</a> ')'  
    '<a href="#wg_soc">WITHIN' 'GROUP' '(' Simple_Order_By_Clause ')</a>'.
</pre>

## Semantics of Syntax Elements 
* <a name="dbl_lit"></a>**`double_literal`**   
The percentile to compute. The value must range between 0.0 and 1.0 and be of type [double](numeric-types-and-literals.md). 

* <a name="wg_soc"></a>**`WITHIN GROUP ( Simple_Order_By_Clause )`**   
  Specifies a list of numeric values to sort and compute the percentile over.  

  ### Syntax
  <pre>
  Simple_Order_By_Clause := 
       'ORDER' 'BY' Sort_Item_Expression.<br />
  Sort_Item_Expression :=     
       expression [Sort_Direction].<br />
  Sort_Direction :=
       'ASC' | 'DESC'.
  </pre>

  Only one [ORDER BY](order-by-and-offset-fetch-clause-u-sql.md) expression is allowed. The type of the expression has to be comparable. The default sort order is ascending. 

## Return Type 
The return type is the type of the [ORDER BY](order-by-and-offset-fetch-clause-u-sql.md) expression. 

## Usage in Windowing Expression  
This analytic function can be used in a [windowing expression](over-expression-u-sql.md) with the following restrictions: 
* Only the [PARTITION BY](over-expression-u-sql.md#OPBC) clause can be specified with the [OVER](over-expression-u-sql.md) operator. 
* The [ORDER BY](over-expression-u-sql.md#OBC) clause in the [OVER](over-expression-u-sql.md) operator is not allowed. 
* The [ROWS](over-expression-u-sql.md#row_cla) clause in the [OVER](over-expression-u-sql.md) operator is not allowed. 

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The example(s) below are based on the dataset(s) defined below.  Ensure your execution includes the rowset variable(s).


**Dataset**   
```sql
@sales = 
    SELECT * FROM 
        ( VALUES
        (1, "A", 100, "FA1", new DateTime(2017,01,01)),
        (1, "A", 200, "FA1", new DateTime(2017,02,01)),
        (1, "A", 300, "FA2", new DateTime(2017,03,01)),
        (1, "A", 400, "GA1", new DateTime(2017,04,01)),
        (2, "B", 400, "FA1", new DateTime(2017,01,01)),
        (2, "B", 300, "FA2", new DateTime(2017,02,01)),
        (2, "B", 200, "FA2", new DateTime(2017,03,01)),
        (2, "B", 100, "FA3", new DateTime(2017,04,01)),
        (3, "B", 200, (string)null, new DateTime(2017,03,01)),
        (3, "B", 225,  "FA3", new DateTime(2017,04,01))
        ) AS T(EmpID, DeptID, Sales, ProductID, SaleDate);
```
<br />

**Using PERCENTILE_DISC - undefined window**   
The following example uses `PERCENTILE_DISC` to find the median sales across all sales.
The `OVER` expression in the following query is empty which defines the "window" to include all rows. 
```sql
@result =
    SELECT  DISTINCT PERCENTILE_DISC(0.5) WITHIN GROUP(ORDER BY Sales) OVER() AS MedianDiscSales
    FROM    @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/percentile_disc/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Using PERCENTILE_DISC - defined window**   
The following example uses `PERCENTILE_DISC` to find the median sales for each department.
The `OVER` expressions in the following query defines windows by partitioning the rowsets on DeptID, and EmpID respectively.
```sql
@result =
    SELECT DISTINCT DeptID, EmpID,
           PERCENTILE_DISC(0.5) WITHIN GROUP(ORDER BY Sales) OVER(PARTITION BY DeptID) AS MedianDiscSalesByDeptID,
           PERCENTILE_DISC(0.5) WITHIN GROUP(ORDER BY Sales) OVER(PARTITION BY EmpID) AS MedianDiscSalesByEmpID
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/percentile_disc/example2.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Using PERCENTILE_DISC, additional examples**   
```sql
@result =
    SELECT DISTINCT DeptID,
                    PERCENTILE_DISC(0.5) WITHIN GROUP(ORDER BY Sales) OVER(PARTITION BY DeptID) AS MedianDiscSalesByDeptID,
                    PERCENTILE_CONT(0.5) WITHIN GROUP(ORDER BY Sales) OVER(PARTITION BY DeptID) AS MedianContSalesByDeptID,
                    AVG(Sales) OVER(PARTITION BY DeptID) AS AverageSaleByDeptID
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/percentile_disc/example3.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />

## See Also 
* [PERCENTILE_CONT()](percentile-cont-u-sql.md)
* [Analytic Functions (U-SQL)](analytic-functions-u-sql.md)  
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
* [PERCENTILE_DISC()](PERCENTILE_DISC%20\(U-SQL\).md)
