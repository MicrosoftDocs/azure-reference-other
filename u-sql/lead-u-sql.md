---
title: "LEAD (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 9c78e14c-65ed-416b-83c0-69b6436a350c
caps.latest.revision: 6
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# LEAD (U-SQL)
The `LEAD` analytic function provides access to a row at a given physical offset that follows the current row. Use this analytic function in a `SELECT` expression to compare values in the current row with values in a following row.

`LEAD` can only be used in the context of a [windowing expression](over-expression-u-sql.md). 

## Syntax
<pre>
LEAD_Expression := 
    'LEAD' '(' <a href="#exp">expression</a> [ ',' <a href="#off">offset</a> ] [ ',' <a href="#def">default</a> ] ')'.
</pre>

## Semantics of Syntax Elements 
* <a name="exp"></a>**`expression`**     
The expression for which the first value gets calculated for the window. 

* <a name="off"></a>**`offset`**  
The number of rows forward from the current row from which to obtain a value. If not specified, the default is 1. `offset` can be an expression that evaluates to a constant positive integral value.  Column references and method calls are not allowed.

* <a name="def"></a>**`default`**  
The value to return when `expression` at `offset` is NULL. If a default value is not specified, NULL is returned. `default` must be a constant and type-compatible with `expression`.  Column references and method calls are not allowed.

## Return Type 
The nullable type of the input. 

## Usage in Windowing Expression 
This analytic function can be used in a [windowing expression](over-expression-u-sql.md) with the following restrictions: 
* The [ORDER BY](over-expression-u-sql.md#OBC) clause in the [OVER](over-expression-u-sql.md) operator is required. 
* The [ROWS](over-expression-u-sql.md#row_cla) clause in the [OVER](over-expression-u-sql.md) operator is not allowed.

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The example(s) below are based on the dataset(s) defined below.  Ensure your execution includes the rowset variable(s).


### Part 1
**Dataset**   
```sql
@storeSales =
    SELECT * FROM 
        ( VALUES
        (1, "NW", 2013, 100),
        (1, "NW", 2014, 150),
        (1, "NW", 2015, 300),
        (1, "NW", 2016, 640),
        (2, "SW", 2013, 200),
        (2, "SW", 2014, 350),
        (2, "SW", 2015, 500),
        (2, "SW", 2016, 650),
        (3, "NW", 2015, 75),
        (3, "NW", 2016, 100),
        (4, "NW", 2016, 375),
        (5, "SW", 2016, 700)
        ) AS T(StoreID, Region, Year, Sales);
```
<br />

**Compare values between years**   
The following example uses the `LEAD` function to return the difference in sales for a specific store over previous years.  Notice that because there is no lead value available for the first row, the default of zero (0) is returned.
```sql
@result =
    SELECT StoreID,
           Year AS SalesYear,
           Sales AS CurrentSales,
           LEAD(Sales, 1, 0) OVER(ORDER BY Year) AS SubsequentSales
    FROM @storeSales
    WHERE StoreID == 1 AND Year >= 2014;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/LEAD/example1A.csv"
ORDER BY SalesYear DESC
USING Outputters.Csv();
```
<br />


**Dividing the result set using PARTITION BY**     
The following example uses the `LEAD` function to compare year-to-date sales between stores.  Each record shows a store's sales and the sales of the store with the nearest higher sales.  The [PARTITION BY](over-expression-u-sql.md#OPBC) clause is specified to divide the rows in the result set by region.  The `LEAD` function is applied to each partition separately and computation restarts for each partition.  The [ORDER BY](over-expression-u-sql.md#OBC) clause in the [OVER](over-expression-u-sql.md) clause orders the rows in each partition.  The [ORDER BY](output-statement-u-sql.md#OBOFC) clause in the [OUTPUT](output-statement-u-sql.md) statement sorts the rows in the whole result set.  Notice that because there is no lead value available for the first row of each partition, the default of zero (0) is returned.
```sql
@result =
    SELECT Region,
           StoreID,
           Sales,
           LEAD(Sales, 1, 0) OVER(PARTITION BY Region ORDER BY Sales ASC) AS NearestHigherSales
    FROM @storeSales
    WHERE Year == 2016;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/LEAD/example1B.csv"
ORDER BY Region, Sales DESC
USING Outputters.Csv();
```
<br />


### Part 2
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


**LEAD with OVER() - undefined window**     
The `OVER` expression in the following query is empty which defines the "window" to include all rows.   
The following example uses the `LEAD` function to return the monthly and subsequent month's sales for a specific employee.
Notice that because there is no `LEAD` value available for the last row, the default of zero (0) is returned.
```sql
@result = 
    SELECT  EmpID, SaleDate.ToShortDateString() AS SaleDate, Sales,
            LEAD(Sales, 1, 0) OVER(ORDER BY SaleDate) AS SubsequentSales
    FROM    @sales
    WHERE   EmpID == 1;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/LEAD/example2A.txt"
USING Outputters.Tsv(outputHeader: true);


// Note: The same result can be obtained with LAG by inverting the ORDER BY in the OVER clause and then reverting the ORDER BY in the OUTPUT.
@result = 
    SELECT  EmpID, SaleDate.ToShortDateString() AS SaleDate, Sales,
            LAG(Sales, 1, 0) OVER(ORDER BY SaleDate DESC) AS SubsequentSales
    FROM @sales
    WHERE   EmpID == 1;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/LEAD/example2B.txt"
ORDER BY SaleDate
USING Outputters.Tsv(outputHeader: true);
```
<br />



**LEAD with OVER() - defined window**  
The `OVER` expression in the following query defines the windows by partitioning the rowset on EmpID.
The following example uses the `LEAD` function to return each employee's monthly and subsequent month's sales. 
The [PARTITION BY](over-expression-u-sql.md#OPBC) clause is specified to divide the rows in the result set by employees. 
The `LEAD` function is applied to each partition separately and computation restarts for each partition. 
The [ORDER BY](over-expression-u-sql.md#OBC) clause in the [OVER](over-expression-u-sql.md) clause orders the rows in each partition. 
Notice that because there is no `LEAD` value available for the last row of each partition, the default of zero (0) is returned.
```sql
@result = 
    SELECT  EmpID, SaleDate.ToShortDateString() AS SaleDate, Sales,
            LEAD(Sales, 1, 0) OVER(PARTITION BY EmpID ORDER BY SaleDate) AS SubsequentSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/LEAD/example2C.txt"
USING Outputters.Tsv(outputHeader: true);


// Note: The same result can be obtained with LAG by inverting the ORDER BY in the OVER clause and then reverting the ORDER BY in the OUTPUT.
@result = 
    SELECT  EmpID, SaleDate.ToShortDateString() AS SaleDate, Sales,
            LAG(Sales, 1, 0) OVER(PARTITION BY EmpID ORDER BY SaleDate DESC) AS SubsequentSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/Analytic/LEAD/example2D.txt"
ORDER BY EmpID, SaleDate
USING Outputters.Tsv(outputHeader: true);
```
<br />



## See Also 
* [LAG (U-SQL)](lag-u-sql.md)
* [FIRST_VALUE (U-SQL)](first-value-u-sql.md)
* [LAST_VALUE (U-SQL)](last-value-u-sql.md)
* [Analytic Functions (U-SQL)](analytic-functions-u-sql.md)  
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 

