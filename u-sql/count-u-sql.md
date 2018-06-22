---
title: "COUNT (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 90746132-b0f2-49b4-8926-6162f935427c
caps.latest.revision: 6
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# COUNT (U-SQL)
The COUNT aggregator returns the number of items in a group. If COUNT(*) is specified the count will include null values, if an expression or column reference is provided, then null values will not be counted. 

The identity value is 0. 

## Syntax
<pre>
COUNT_Expression := 
    'COUNT' '(' ['<a href="#dist">DISTINCT</a>'] (<a href="#exp">expression | '*'</a>) ')'.  
</pre>

## Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**  
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation.  

* <a name="exp"></a>**`expression | *`**   
The C# expression (including column references) for which the nonnull values in a group get counted or * to indicate to count the rows and include null values in the count. 

## Return Type 
The return type is [long?](numeric-types-and-literals.md). 

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

**Count of all records**  
The following query calculates: 1) the total record count, 2) total ProductID count, and 3) the count of distinct EmpIDs.
```sql
@result =
    SELECT  COUNT( * ) AS TotalRecordCount,
            COUNT(ProductID) AS ProductIDCount,
            COUNT(DISTINCT EmpID) AS DistinctEmpIDCount
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/COUNT/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Count values per group**   
The following query calculates the count of sales within each department with the `GROUP BY` clause.
```sql
@result =
    SELECT DeptID,
           COUNT(*) AS SalesCountByDept
    FROM @sales
    GROUP BY DeptID;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/COUNT/example2.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Count with OVER() - undefined window**  
The `OVER` expression in the following query is empty which defines the "window" to include all rows.   
The query calculates the sale count over the window - all sales.
```sql
@result =
    SELECT DISTINCT COUNT(*) OVER() AS SalesCount
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/COUNT/example3.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Count with OVER() - defined window**   
The `OVER` expressions in the following query defines the windows by partitioning the rowsets on EmpID, and DeptID respectively.  
The query returns EmpID, DeptID, and the sales count over each window - EmpID, and DeptID respectively.
```sql
@result =
    SELECT DISTINCT EmpID, DeptID,
           COUNT(*) OVER(PARTITION BY EmpID) AS SalesCountByEmployee,
           COUNT(*) OVER(PARTITION BY DeptID) AS SalesCountByDepartment
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/COUNT/example4.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Filtering Results of Aggregate Values**  
The `HAVING` clause restricts the result set to those records with a SalesCountByEmpID value greater than 2.
```sql
@result =
    SELECT EmpID,
           COUNT(Sales) AS SalesCountByEmpID
    FROM @sales
    GROUP BY EmpID
    HAVING COUNT(Sales) > 2;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/COUNT/example5A.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Alternative, less efficient method using OVER()**  
Windowed functions (those with an `OVER` clause) are only allowed in a query that has no row grouping of any kind.
```sql
@result =
    SELECT DISTINCT s.EmpID, sa.SalesCountByEmpID
    FROM @sales AS s
    JOIN (SELECT EmpID, COUNT(Sales) OVER(PARTITION BY EmpID) AS SalesCountByEmpID FROM @sales) AS sa
    ON s.EmpID == sa.EmpID
    WHERE sa.SalesCountByEmpID > 2;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/COUNT/example5B.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Counts using OVER() in a calculated value**   
The `OVER` expression in the following query defines the window by partitioning the rowset on EmpID. 
The query returns each EmpID's total sales count, the overall total sales count, and each EmpID's share of the total sales count.
```sql
@result =
    SELECT DISTINCT EmpID, 
           COUNT(*) OVER(PARTITION BY EmpID) AS SalesCountByEmployee,
           COUNT(*) OVER() AS SalesCountTotal,            
           (COUNT(*) OVER(PARTITION BY EmpID) / (decimal)COUNT(*) OVER()) * 100 AS EmployeesPercentOfSalesCountTotal
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/COUNT/example6.csv"
USING Outputters.Csv(outputHeader: true);
```

**Count using OVER() and the ROWS clause**   
The `OVER` expression in the following query defines the window by partitioning the rowset on EmpID.   
The `ROWS` clause further limits the rows in the partition by specifying fixed number of rows preceding or following the current row.
```sql
@result =
    SELECT EmpID,
           SaleDate.ToShortDateString() AS SaleDate,
           COUNT(*) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS threeMonthWindow_2PriorAndCurrent_ByEmpID,
           COUNT(*) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING) AS threeMonthWindow_1Prior_Current_1Following_ByEmpID,
           COUNT(*) OVER(ORDER BY EmpID, SaleDate ROWS UNBOUNDED PRECEDING) AS rollingCount_allSales,
           COUNT(*) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS UNBOUNDED PRECEDING) AS rollingCount_ByEmpID           
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/COUNT/example7.csv"
ORDER BY EmpID, SaleDate
USING Outputters.Csv(outputHeader: true);
```

**Count using OVER() with a multi-column partition**   
The `OVER` expression in the following query defines the window by partitioning the rowset on both ProductID and SaleDate.  
Query returns the sale count for each ProductID and SaleDate.
```sql
@result =
    SELECT  DISTINCT ProductID,
            SaleDate.ToShortDateString() AS SaleDate,
            COUNT(*) OVER(PARTITION BY ProductID, SaleDate) AS SaleCountByProductIDAndDate
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/COUNT/example8A.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Same as above without OVER() and using GROUP BY**  
```sql
@result =
    SELECT ProductID,
           SaleDate.ToShortDateString() AS SaleDate,
           COUNT(*) AS SaleCountByProductIDAndDate
    FROM @sales
    GROUP BY ProductID, SaleDate;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/COUNT/example8B.txt"
USING Outputters.Tsv(outputHeader: true);
```

## See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
