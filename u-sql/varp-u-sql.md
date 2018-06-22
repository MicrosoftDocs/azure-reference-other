---
title: "VARP (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 398fe8e3-a16c-4dea-b437-a7074fc4cbde
caps.latest.revision: 6
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# VARP (U-SQL)
The `VARP` aggregator returns the statistical variance for the population for all nonnull values in the group or returns null if all the input values are null. The values have to be numeric or an error is raised. 

The identity value is null.  There must be at least two values in the set of values for a statistical variance calculation.

## Syntax
<pre>
VARP_Expression :=
     'VARP' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'.
</pre>

## Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**     
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation.  

* <a name="exp"></a>**`expression`**     
The C# expression (including column references) that gets aggregated. The type of the expression has to be a numeric type or an error is raised. 

## Return Type 
The return type is [double?](numeric-types-and-literals.md). 

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


**Statistical variance (population) of all values**  
The following query returns the statistical variance for the population for all sales values and from all `DISTINCT` sales values.
```sql
@result =
    SELECT VARP(Sales) AS VARP_AllSales,
           VARP(DISTINCT Sales) AS VARP_DistinctSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/VARP/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Statistical variance (population) per group**   
The following query returns the statistical variance for the population for all sales values for each employee with the `GROUP BY` clause.
```sql
@result =
    SELECT EmpID,
           VARP(Sales) AS VARP_SalesByEmployee
    FROM @sales
    GROUP BY EmpID;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/VARP/example2.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Statistical variance (population) with OVER() - undefined window**  
The `OVER` expression in the following query is empty which defines the "window" to include all rows.   
The query returns the statistical variance for the population for sales over the window - all sales.
```sql
@result =
    SELECT  DISTINCT VARP(Sales) OVER() AS VARP_AllSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/VARP/example3.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Statistical variance (population) with OVER() - defined window**  
The `OVER` expressions in the following query defines the windows by partitioning the rowsets on EmpID, and DeptID respectively.
The query returns EmpID, DeptID, and the statistical variance for the population for sales over each window - EmpID, and DeptID respectively.
```sql
@result =
    SELECT DISTINCT EmpID, DeptID,
           VARP(Sales) OVER(PARTITION BY EmpID) AS VARP_SalesByEmployee,
           VARP(Sales) OVER(PARTITION BY DeptID) AS VARP_SalesByDepartment
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/VARP/example4.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Filtering Results of Aggregate Values**  
The `HAVING` clause restricts the result set to those records with a `VARP_SalesByEmployee` value greater than 1000.
```sql
@result =
    SELECT EmpID,
           VARP(Sales) AS VARP_SalesByEmployee
    FROM @sales
    GROUP BY EmpID
    HAVING VARP(Sales) > 1000;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/VARP/example5A.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Alternative, less efficient method using OVER()**  
Windowed functions (those with an `OVER` clause) are only allowed in a query that has no row grouping of any kind.
```sql
@result =
    SELECT DISTINCT s.EmpID, sa.VARP_SalesByEmployee
    FROM @sales AS s
    JOIN (SELECT EmpID, VARP(Sales) OVER(PARTITION BY EmpID) AS VARP_SalesByEmployee FROM @sales) AS sa
    ON s.EmpID == sa.EmpID
    WHERE sa.VARP_SalesByEmployee > 1000;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/VARP/example5B.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Statistical variance (population) using OVER() and the ROWS clause**  
The `OVER` expression in the following query defines the window by partitioning the rowset on EmpID.   
The `ROWS` clause further limits the rows in the partition by specifying fixed number of rows preceding or following the current row.
```sql
@result =
    SELECT EmpID,
           SaleDate.ToShortDateString() AS SaleDate,
           Sales AS currentSales,
           VARP(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS threeMonthVARP_2PriorAndCurrent_ByEmpID  ,
           VARP(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING) AS threeMonthVARP_1Prior_Current_1Following_ByEmpID  ,
           VARP(Sales) OVER(ORDER BY EmpID, SaleDate ROWS UNBOUNDED PRECEDING) AS rollingVARP_allSales,
           VARP(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS UNBOUNDED PRECEDING) AS rollingVARP_ByEmpID             
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/VARP/example6.csv"
ORDER BY EmpID, SaleDate
USING Outputters.Csv(outputHeader: true);
```
<br />


**Statistical variance (population) using OVER() with a multi-column partition**  
The `OVER` expression in the following query defines the window by partitioning the rowset on both DeptID and ProductID.   
Query returns the statistical variance for the population for sales for each DeptID and ProductID.
```sql
@result =
    SELECT  DISTINCT DeptID, ProductID,
            VARP(Sales) OVER(PARTITION BY DeptID, ProductID) AS VARP_SalesByDeptIDAndProductID
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/VARP/example7A.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Same as above without OVER() and using GROUP BY**  
```sql
@result =
    SELECT DeptID, ProductID,
           VARP(Sales) AS VARP_SalesByDeptIDAndProductID
    FROM @sales
    GROUP BY DeptID, ProductID;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/VARP/example7B.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


## See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)   
* [VAR (U-SQL)](var-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](over-expression-u-sql.md)  

