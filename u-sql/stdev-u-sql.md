---
title: "STDEV (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 5b2bd234-3fd5-4392-95d5-18bb3df9dc5a
caps.latest.revision: 6
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# STDEV (U-SQL)
The `STDEV` aggregator returns the statistical standard deviation of all nonnull values in the group or returns null if all the input values are null. The values have to be numeric or an error is raised. 

The identity value is null. 

There must be at least two values in the set of values for a standard deviation calculation.

## Syntax
<pre>
STDEV_Expression := 
    'STDEV' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'.
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

**Standard deviation of all values**   
The following query returns the standard deviation for all sales values and from all `DISTINCT` sales values.
```sql
@result =
    SELECT STDEV(Sales) AS STDEV_AllSales,
           STDEV(DISTINCT Sales) AS STDEV_DistinctSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEV/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />

**Standard deviation per group**   
The following query returns the standard deviation for all sales values for each employee with the `GROUP BY` clause.
```sql
@result =
    SELECT EmpID,
           STDEV(Sales) AS STDEV_SalesByEmployee
    FROM @sales
    GROUP BY EmpID;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEV/example2.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />

**Standard deviation with OVER() - undefined window**  
The `OVER` expression in the following query is empty which defines the "window" to include all rows.  
The query returns the standard deviation for sales over the window - all sales.
```sql
@result =
    SELECT  DISTINCT STDEV(Sales) OVER() AS STDEV_AllSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEV/example3.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />

**Standard deviation with OVER() - defined window**  
The `OVER` expressions in the following query defines the windows by partitioning the rowsets on EmpID, and DeptID respectively.  
The query returns EmpID, DeptID, and the standard deviation for sales over each window - EmpID, and DeptID respectively.
```sql
@result =
    SELECT DISTINCT EmpID, DeptID,
           STDEV(Sales) OVER(PARTITION BY EmpID) AS STDEV_SalesByEmployee,
           STDEV(Sales) OVER(PARTITION BY DeptID) AS STDEV_SalesByDepartment
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEV/example4.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />

**Filtering Results of Aggregate Values**   
The `HAVING` clause restricts the result set to those records with a `STDEV_SalesByEmployee` value greater than 100.
```sql
@result =
    SELECT EmpID,
           STDEV(Sales) AS STDEV_SalesByEmployee
    FROM @sales
    GROUP BY EmpID
    HAVING STDEV(Sales) > 100;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEV/example5A.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />

**Alternative, less efficient method using OVER()**   
Windowed functions (those with an `OVER` clause) are only allowed in a query that has no row grouping of any kind.
```sql
@result =
    SELECT DISTINCT s.EmpID, sa.STDEV_SalesByEmployee
    FROM @sales AS s
    JOIN (SELECT EmpID, STDEV(Sales) OVER(PARTITION BY EmpID) AS STDEV_SalesByEmployee FROM @sales) AS sa
    ON s.EmpID == sa.EmpID
    WHERE sa.STDEV_SalesByEmployee > 100;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEV/example5B.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />

**Standard deviation using OVER() and the ROWS clause**   
The `OVER` expression in the following query defines the window by partitioning the rowset on EmpID.   
The `ROWS` clause further limits the rows in the partition by specifying fixed number of rows preceding or following the current row.
```sql
@result =
    SELECT EmpID,
           SaleDate.ToShortDateString() AS SaleDate,
           Sales AS currentSales,
           STDEV(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS threeMonthSTDEV_2PriorAndCurrent_ByEmpID ,
           STDEV(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING) AS threeMonthSTDEV_1Prior_Current_1Following_ByEmpID ,
           STDEV(Sales) OVER(ORDER BY EmpID, SaleDate ROWS UNBOUNDED PRECEDING) AS rollingSTDEV_allSales,
           STDEV(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS UNBOUNDED PRECEDING) AS rollingSTDEV_ByEmpID             
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEV/example6.csv"
ORDER BY EmpID, SaleDate
USING Outputters.Csv(outputHeader: true);
```
<br />

**Standard deviation using OVER() with a multi-column partition**  
The `OVER` expression in the following query defines the window by partitioning the rowset on both DeptID and ProductID.   
Query returns the standard deviation for sales for each DeptID and ProductID.
```sql
@result =
    SELECT  DISTINCT DeptID, ProductID,
            STDEV(Sales) OVER(PARTITION BY DeptID, ProductID) AS STDEV_SalesByDeptIDAndProductID
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEV/example7A.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />

**Same as above without OVER() and using GROUP BY**  
```sql
@result =
    SELECT DeptID, ProductID,
           STDEV(Sales) AS STDEV_SalesByDeptIDAndProductID
    FROM @sales
    GROUP BY DeptID, ProductID;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/STDEV/example7B.txt"
USING Outputters.Tsv(outputHeader: true);
```


## See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)   
* [STDEVP (U-SQL)](stdevp-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
