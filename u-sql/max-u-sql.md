---
title: "MAX (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 3e0f1b7d-66e5-4e5f-bbd8-6e4de221eda5
caps.latest.revision: 7
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# MAX (U-SQL)
The MAX aggregator choses the largest value in the group or null if the expression returns only nulls in the group. The values have to be comparable. For string types, it uses a culture-invariant UTF-8 byte ordering. 

The identity value is null. 

## Syntax
<pre>
MAX_Expression := 
    'MAX' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'.
</pre>

## Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**     
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation. DISTINCT is not meaningful with MAX and is available for ISO compatibility only. 

* <a name="exp"></a>**`expression`**    
The C# expression (including column references) that gets aggregated. Its result type has to be comparable. 

## Return Type 
The nullable type of the input. 

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

**Highest of all values**   
The following query returns the single highest Sales figure.
```sql
@result =
    SELECT MAX(Sales) AS HighestSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/MAX/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Highest values per group**   
The following query returns the highest sales figure for each SaleDate with the `GROUP BY` clause.
```sql
@result =
    SELECT SaleDate.ToShortDateString() AS SaleDate,
           MAX(Sales) AS HighestSalesBySaleDate
    FROM @sales
    GROUP BY SaleDate;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/MAX/example2.txt"
USING Outputters.Tsv(outputHeader: true);
```
 
**Highest values with OVER() - undefined window**   
The `OVER` expression in the following query is empty which defines the "window" to include all rows.   
The query calculates the highest sales over the window - all sales.
The query returns EmpID, SaleDate, Sales, and the highest overall Sales.
```sql
@result =
    SELECT  EmpID, 
            SaleDate.ToShortDateString() AS SaleDate,
            Sales,
            MAX(Sales) OVER() AS HighestOverallSales
    FROM    @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/MAX/example3.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Highest values with OVER() - defined window**   
The first `OVER` expression in the following query defines the window by partitioning the rowset on SaleDate.    
The query returns SaleDate, the highest sales for each SaleDate, and the highest sales overall.
```sql
@result =
    SELECT DISTINCT SaleDate.ToShortDateString() AS SaleDate,
           MAX(Sales) OVER(PARTITION BY SaleDate) AS HighestSalesBySaleDate,
           MAX(Sales) OVER() AS HighestOverallSales
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/MAX/example4.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Filtering Results of Aggregate Values**  
The `HAVING` clause restricts the result set to those records where an employee's highest sale is less than 300.  
As opposed to those records where an employee has any sale less than 300.
```sql
@result =
    SELECT EmpID, 
           MAX(Sales) AS FilteredSalesByEmployee
    FROM @sales
    GROUP BY EmpID
    HAVING MAX(Sales) < 300;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/MAX/example5A.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Alternative, less efficient method using OVER()**   
Windowed functions (those with an OVER clause) are only allowed in a query that has no row grouping of any kind.
```sql
@result =
    SELECT DISTINCT s.EmpID, 
            sa.FilteredSalesByEmployee
    FROM @sales AS s
    JOIN (SELECT EmpID, (int)MAX(Sales) OVER(PARTITION BY EmpID) AS FilteredSalesByEmployee FROM @sales) AS sa
    ON s.EmpID == sa.EmpID
    AND s.Sales == sa.FilteredSalesByEmployee
    WHERE sa.FilteredSalesByEmployee < 300;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/MAX/example5B.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Highest values using OVER() in a calculated value**  
The `OVER` expression in the following query defines the window by partitioning the rowset on EmpID.   
The query returns each EmpID's monthly sales, the highest sales for each EmpID and the difference between current sales and highest sales.
```sql
@result =
    SELECT EmpID, 
           SaleDate.ToShortDateString() AS SaleDate,
           Sales, 
           MAX(Sales) OVER(PARTITION BY EmpID) AS MaxSaleByEmpID,
           Sales - MAX(Sales) OVER(PARTITION BY EmpID) AS DifferenceFromMaxSaleByEmpID
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/MAX/example6.csv"
USING Outputters.Csv(outputHeader: true);
```

**MAX values using OVER() and the ROWS clause**   
The `OVER` expression in the following query defines the window by partitioning the rowset on EmpID.   
The `ROWS` clause further limits the rows in the partition by specifying fixed number of rows preceding or following the current row.
```sql
@result =
    SELECT EmpID,
           SaleDate.ToShortDateString() AS SaleDate,
           Sales AS currentSales,
           MAX(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS threeMonthMax_2PriorAndCurrent_ByEmpID,
           MAX(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING) AS threeMonthMax_1Prior_Current_1Following_ByEmpID,
           MAX(Sales) OVER(ORDER BY EmpID, SaleDate ROWS UNBOUNDED PRECEDING) AS rollingMax_allSales,
           MAX(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS UNBOUNDED PRECEDING) AS rollingMax_ByEmpID  
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/MAX/example7.csv"
//ORDER BY EmpID, SaleDate
USING Outputters.Csv(outputHeader: true);
```

**Highest values using OVER() with a multi-column partition**   
The `OVER` expression in the following query defines the window by partitioning the rowset on both ProductID and SaleDate.   
Query returns the highest sales for each ProductID and SaleDate.
```sql
@result =
    SELECT  DISTINCT ProductID,
            SaleDate.ToShortDateString() AS SaleDate, 
            MAX(Sales) OVER(PARTITION BY ProductID, SaleDate) AS HighestSalesByProductIDAndSaleDate
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/MAX/example8A.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Same as above without OVER() and using GROUP BY**  
```sql
@result =
    SELECT  ProductID,
            SaleDate.ToShortDateString() AS SaleDate, 
            MAX(Sales) AS HighestSalesByProductIDAndSaleDate
    FROM @sales
    GROUP BY ProductID, SaleDate;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/MAX/example8B.txt"
USING Outputters.Tsv(outputHeader: true);
```

## See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
