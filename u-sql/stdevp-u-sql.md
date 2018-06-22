---
title: "STDEVP (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 5a492d5b-08a8-4e59-8355-a386be47c26f
caps.latest.revision: 6
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# STDEVP (U-SQL)
The STDEVP aggregator returns the statistical standard deviation for the population for all nonnull values in the group or returns null if all the input values are null. The values have to be numeric or an error is raised. 

The identity value is null. 

## Syntax
<pre>
STDEVP_Expression :=  
    'STDEVP' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'.
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

**Standard deviation (population) of all values**  
The following query returns the standard deviation for the population for all sales values and from all `DISTINCT` sales values.
```sql
@result =
    SELECT STDEVP(Sales) AS STDEVP_AllSales,
           STDEVP(DISTINCT Sales) AS STDEVP_DistinctSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEVP/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Standard deviation (population) per group**  
The following query returns the standard deviation for the population for all sales values for each employee with the `GROUP BY` clause.
```sql
@result =
    SELECT EmpID,
           STDEVP(Sales) AS STDEVP_SalesByEmployee
    FROM @sales
    GROUP BY EmpID;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEVP/example2.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Standard deviation (population) with OVER() - undefined window**   
The `OVER` expression in the following query is empty which defines the "window" to include all rows.   
The query returns the standard deviation for the population for sales over the window - all sales.
```sql
@result =
    SELECT  DISTINCT STDEVP(Sales) OVER() AS STDEVP_AllSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEVP/example3.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Standard deviation (population) with OVER() - undefined window**  
The `OVER` expressions in the following query defines the windows by partitioning the rowsets on EmpID, and DeptID respectively.
The query returns EmpID, DeptID, and the standard deviation for the population for sales over each window - EmpID, and DeptID respectively.
```sql
@result =
    SELECT DISTINCT EmpID, DeptID,
           STDEVP(Sales) OVER(PARTITION BY EmpID) AS STDEVP_SalesByEmployee,
           STDEVP(Sales) OVER(PARTITION BY DeptID) AS STDEVP_SalesByDepartment
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEVP/example4.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Filtering Results of Aggregate Values**   
The `HAVING` clause restricts the result set to those records with a `STDEVP_SalesByEmployee` value greater than 100.
```sql
    SELECT EmpID,
           STDEVP(Sales) AS STDEVP_SalesByEmployee
    FROM @sales
    GROUP BY EmpID
    HAVING STDEVP(Sales) > 100;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEVP/example5A.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Alternative, less efficient method using OVER()**   
Windowed functions (those with an `OVER` clause) are only allowed in a query that has no row grouping of any kind.
```sql
@result =
    SELECT DISTINCT s.EmpID, sa.STDEVP_SalesByEmployee
    FROM @sales AS s
    JOIN (SELECT EmpID, STDEVP(Sales) OVER(PARTITION BY EmpID) AS STDEVP_SalesByEmployee FROM @sales) AS sa
    ON s.EmpID == sa.EmpID
    WHERE sa.STDEVP_SalesByEmployee > 100;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEVP/example5B.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Standard deviation (population) using OVER() and the ROWS clause**   
The `OVER` expression in the following query defines the window by partitioning the rowset on EmpID.    
The `ROWS` clause further limits the rows in the partition by specifying fixed number of rows preceding or following the current row.
```sql
@result =
    SELECT EmpID,
           SaleDate.ToShortDateString() AS SaleDate,
           Sales AS currentSales,
           STDEVP(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS threeMonthSTDEVP_2PriorAndCurrent_ByEmpID,
           STDEVP(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING) AS threeMonthSTDEVP_1Prior_Current_1Following_ByEmpID,
           STDEVP(Sales) OVER(ORDER BY EmpID, SaleDate ROWS UNBOUNDED PRECEDING) AS rollingSTDEVP_allSales,
           STDEVP(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS UNBOUNDED PRECEDING) AS rollingSTDEVP_ByEmpID           
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEVP/example6.csv"
ORDER BY EmpID, SaleDate
USING Outputters.Csv(outputHeader: true);
```
<br />


**Standard deviation (population) using OVER() with a multi-column partition**    
The `OVER` expression in the following query defines the window by partitioning the rowset on both DeptID and ProductID.     
Query returns the standard deviation for the population for sales for each DeptID and ProductID.
```sql
@result =
    SELECT  DISTINCT DeptID, ProductID,
            STDEVP(Sales) OVER(PARTITION BY DeptID, ProductID) AS STDEVP_SalesByDeptIDAndProductID
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEVP/example7A.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Same as above without OVER() and using GROUP BY**  
```sql
@result =
    SELECT DeptID, ProductID,
           STDEVP(Sales) AS STDEVP_SalesByDeptIDAndProductID
    FROM @sales
    GROUP BY DeptID, ProductID;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEVP/example7B.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


 
## See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)  
* [STDEV (U-SQL) ](stdev-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
