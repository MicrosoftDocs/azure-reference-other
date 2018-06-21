---
title: "AVG (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: df66e28f-2098-4a64-ae11-f3339fad677d
caps.latest.revision: 7
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# AVG (U-SQL)
The AVG aggregator computes the average of a set of numeric values by dividing the sum of those values by the count of nonnull values. If the sum exceeds the maximum value for the data type of the return value an error will be returned. 

The identity value is null. 

## Syntax
<pre>
AVG_Expression := 
    'AVG' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'.
</pre>

## Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**  
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation.  

* <a name="exp"></a>**`expression`**  
The C# expression (including column references) that gets aggregated. The type of the expression has to be a numeric or nullable numeric type, otherwise an error is raised. 

## Return Type 
The return type is determined by the type of the evaluated result of the expression as follows: 

|Expression type|Return type|Comment| 
|---|---|---|
|Integral types (short, int, uint, etc) implicitly castable to long and long?| long?|To be aligned with SQL semantics. The resulting value will be truncated to its integral part.| 
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

**Average of all values**    
The following query calculates the average sales 1) from all sales, and 2) from all `DISTINCT` `Sales` values.
```sql
@result =
    SELECT AVG(Sales) AS AverageSales,
           AVG((double)Sales) AS AverageSales_nonTruncated,
           AVG(DISTINCT Sales) AS AverageDistinctSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/AVG/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Average values per group**   
The following query calculates the average sales for each employee with the `GROUP BY` clause.
```sql
@result =
    SELECT EmpID,
           AVG(Sales) AS AverageSalesByEmployee
    FROM @sales
    GROUP BY EmpID;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/AVG/example2.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Average values with OVER() - undefined window**   
The `OVER` expression in the following query is empty which defines the "window" to include all rows.   
The query calculates the average sales over the window - all sales.
```sql
@result =
    SELECT DISTINCT AVG(Sales) OVER() AS AverageSalesAllSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/AVG/example3.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Average values with OVER() - defined window**   
The `OVER` expressions in the following query defines the windows by partitioning the rowsets on EmpID, and DeptID respectively.  
The query returns EmpID, DeptID, and the average salary over each window - EmpID, and DeptID respectively.
```sql
@result =
    SELECT DISTINCT EmpID, DeptID,
           AVG(Sales) OVER(PARTITION BY EmpID) AS AverageSalesByEmployee,
           AVG(Sales) OVER(PARTITION BY DeptID) AS AverageSalesByDepartment
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/AVG/example4.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Filtering Results of Aggregate Values**   
The `HAVING` clause restricts the result set to those records with an AverageSalesByEmployee value greater than 225.
```sql
@result =
    SELECT EmpID,
           AVG(Sales) AS AverageSalesByEmployee
    FROM @sales
    GROUP BY EmpID
    HAVING AVG(Sales) > 225;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/AVG/example5A.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Alternative, less efficient method using OVER().**  
Windowed functions (those with an `OVER` clause) are only allowed in a query that has no row grouping of any kind.
```sql
@result =
    SELECT DISTINCT s.EmpID, sa.AverageSalesByEmployee
    FROM @sales AS s
    JOIN (SELECT EmpID, AVG(Sales) OVER(PARTITION BY EmpID) AS AverageSalesByEmployee FROM @sales) AS sa
    ON s.EmpID == sa.EmpID
    WHERE sa.AverageSalesByEmployee > 225;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/AVG/example5B.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Average values using `OVER()` in a calculated value**  
The `OVER` expression in the following query defines the window by partitioning the rowset on DeptID.   
The query returns each EmpID's monthly sales, the average sales for each DeptID and the difference between EmpID's current sales and DeptID's average sales.
```sql
@result =
    SELECT DeptID, EmpID,
           SaleDate.ToShortDateString() AS SaleDate,
           Sales, 
           AVG(Sales) OVER(PARTITION BY DeptID) AS AvgSalesByDept,
           Sales - AVG(Sales) OVER(PARTITION BY DeptID) AS DifferenceFromAvgSalesByDept
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/AVG/example6.csv"
USING Outputters.Csv(outputHeader: true);
```

**Average values using OVER() and the ROWS clause**  
The `OVER` expression in the following query defines the window by partitioning the rowset on EmpID.   
The `ROWS` clause further limits the rows in the partition by specifying fixed number of rows preceding or following the current row.
```sql
@result =
    SELECT EmpID,
           SaleDate.ToShortDateString() AS SaleDate,
           Sales AS currentSales,
           AVG(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS threeMonthAvg_2PriorAndCurrent_ByEmpID,
           AVG(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING) AS threeMonthAvg_1Prior_Current_1Following_ByEmpID,
           AVG(Sales) OVER(ORDER BY EmpID, SaleDate ROWS UNBOUNDED PRECEDING) AS rollingAverage_allSales,
           AVG(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS UNBOUNDED PRECEDING) AS rollingAverage_ByEmpID            
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/AVG/example7.csv"
ORDER BY EmpID, SaleDate
USING Outputters.Csv(outputHeader: true);
```

**Average values using OVER() with a multi-column partition**   
The `OVER` expression in the following query defines the window by partitioning the rowset on both DeptID and ProductID.   
Query returns the average sales for each DeptID and ProductID.  
```sql
@result =
    SELECT  DISTINCT DeptID, ProductID,
            AVG(Sales) OVER(PARTITION BY DeptID, ProductID) AS AverageSalesByDeptIDAndProductID
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/AVG/example8A.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Same as above without OVER() and using GROUP BY**  
```sql
@result =
    SELECT DeptID, ProductID,
           AVG(Sales) AS AverageSalesByDeptIDAndProductID
    FROM @sales
    GROUP BY DeptID, ProductID;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/AVG/example8B.txt"
USING Outputters.Tsv(outputHeader: true);
```


## See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
