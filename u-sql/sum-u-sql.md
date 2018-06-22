---
title: "SUM (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 39f0b7a8-d3cd-4511-a124-e89ca12008ee
caps.latest.revision: 6
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# SUM (U-SQL)
The `SUM` aggregator returns the sum of all the values in the group. The input values have to be of a numeric type or an error is raised. Null values are ignored. 

The identity value is null. 

## Syntax
<pre>
SUM_Expression :=   
    'SUM' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'.
</pre>

## Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**    
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation.  

* <a name="exp"></a>**`expression`**     
The C# expression (including column references) that gets aggregated. Its type has to be a numeric type or an error is raised. 

## Return Type 
The return type is determined by the type of the evaluated result of the expression as follows: 

|Expression type|Return type|Comment| 
|--|--|--|
|Integral types (short, int, uint, etc) implicitly castable to long and long?| long?|To be aligned with SQL semantics.|  
|ulong, ulong?|double?|Returns double to be able to handle large values.| 
|decimal, decimal?|decimal?||
|float, float?, double, double?|double?|| 

## Usage in Windowing Expression 
This aggregator can be used in a [windowing expression](over-expression-u-sql.md) without any additional restrictions. 

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


**Total of all values**  
The following query calculates the 1) total sales, and 2) total sales from all `DISTINCT` sales values.
```sql
@result =
    SELECT SUM(Sales) AS TotalSales,
           SUM(DISTINCT Sales) AS TotalDistinctSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/SUM/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Total values per group**  
The following query calculates the total sales for each employee with the `GROUP BY` clause.
```sql
@result =
    SELECT EmpID,
           SUM(Sales) AS TotalSalesByEmployee
    FROM @sales
    GROUP BY EmpID;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/SUM/example2.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Total values with OVER() - undefined window**  
The `OVER` expression in the following query is empty which defines the "window" to include all rows.    
The query calculates the total sales over the window - all sales.
```sql
@result =
    SELECT DISTINCT SUM(Sales) OVER() AS TotalSalesAllSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/SUM/example3.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Total values with OVER() - defined window**  
The `OVER` expressions in the following query defines the windows by partitioning the rowsets on EmpID, and DeptID respectively.
The query returns EmpID, DeptID, and the average salary over each window - EmpID, and DeptID respectively.
```sql
@result =
    SELECT DISTINCT EmpID, DeptID,
           SUM(Sales) OVER(PARTITION BY EmpID) AS TotalSaleByEmployee,
           SUM(Sales) OVER(PARTITION BY DeptID) AS TotalSaleByDepartment
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/SUM/example4.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Filtering Results of Aggregate Values**   
The `HAVING` clause restricts the result set to those records with a `TotalSalesByEmployee` value greater than 500.
```sql
@result =
    SELECT EmpID,
           SUM(Sales) AS TotalSalesByEmployee
    FROM @sales
    GROUP BY EmpID
    HAVING SUM(Sales) > 500;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/SUM/example5A.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Alternative, less efficient method using OVER()**   
Windowed functions (those with an `OVER` clause) are only allowed in a query that has no row grouping of any kind.
```sql
@result =
    SELECT DISTINCT s.EmpID, sa.TotalSalesByEmployee
    FROM @sales AS s
    JOIN (SELECT EmpID, SUM(Sales) OVER(PARTITION BY EmpID) AS TotalSalesByEmployee FROM @sales) AS sa
    ON s.EmpID == sa.EmpID
    WHERE sa.TotalSalesByEmployee > 500;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/SUM/example5B.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Total values using OVER() in a calculated value**   
The `OVER` expression in the following query defines the window by partitioning the rowset on EmpID.    
The query returns each EmpID's monthly sales, the total sales for each EmpID and the difference between current sales and total sales.
```sql
@result =
    SELECT EmpID, 
           SaleDate.ToShortDateString() AS SaleDate,
           Sales, 
           SUM(Sales) OVER(PARTITION BY EmpID) AS TotalSalesByEmpID,
           ((decimal)Sales / SUM(Sales) OVER(PARTITION BY EmpID)) * 100 AS PercentOfTotalSalesByEmpID
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/SUM/example6.csv"
USING Outputters.Csv(outputHeader: true);
```
<br />


**Total values using OVER() and the ROWS clause**   
The `OVER` expression in the following query defines the window by partitioning the rowset on EmpID.   
The `ROWS` clause further limits the rows in the partition by specifying fixed number of rows preceding or following the current row.
```sql
@result =
    SELECT EmpID,
           SaleDate.ToShortDateString() AS SaleDate,
           Sales AS currentSales,
           SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS threeMonthTotal_2PriorAndCurrent_ByEmpID,
           SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING) AS threeMonthTotal_1Prior_Current_1Following_ByEmpID,
           SUM(Sales) OVER(ORDER BY EmpID, SaleDate ROWS UNBOUNDED PRECEDING) AS rollingTotal_allSales,
           SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS UNBOUNDED PRECEDING) AS rollingTotal_ByEmpID        
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/SUM/example7.csv"
ORDER BY EmpID, SaleDate
USING Outputters.Csv(outputHeader: true);
```
<br />


**Total values using OVER() with a multi-column partition**   
The `OVER` expression in the following query defines the window by partitioning the rowset on both DeptID and ProductID.    
Query returns the total sales for each DeptID and ProductID.
```sql
@result =
    SELECT  DISTINCT DeptID, ProductID,
            SUM(Sales) OVER(PARTITION BY DeptID, ProductID) AS TotalSalesByDeptIDAndProductID
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/SUM/example8A.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Same as above without OVER() and using GROUP BY**  
```sql
@result =
    SELECT DeptID, ProductID,
           SUM(Sales) AS TotalSalesByDeptIDAndProductID
    FROM @sales
    GROUP BY DeptID, ProductID;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/SUM/example8B.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


## See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
