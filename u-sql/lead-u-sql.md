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
The LEAD analytic function provides access to a row at a given physical offset that follows the current row. Use this analytic function in a SELECT expression to compare values in the current row with values in a following row.

LEAD can only be used in the context of a [windowing expression](over-expression-u-sql.md). 

<table><th align="left">Syntax</th><tr><td><pre>
LEAD_Expression :=                                                                                
     'LEAD' '(' <a href="#exp">expression</a> [ ',' <a href="#off">offset</a> ] [ ',' <a href="#def">default</a> ] ')'.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="exp"></a>**`expression`**     
The expression for which the first value gets calculated for the window. 

* <a name="off"></a>**`offset`**  
The number of rows forward from the current row from which to obtain a value. If not specified, the default is 1. `offset` can be an expression that evaluates to a constant positive integral value.  Column references and method calls are not allowed.

* <a name="def"></a>**`default`**  
The value to return when `expression` at `offset` is NULL. If a default value is not specified, NULL is returned. `default` must be a constant and type-compatible with `expression`.  Column references and method calls are not allowed.

### Return Type 
The nullable type of the input. 

### Usage in Windowing Expression 
This analytic function can be used in a [windowing expression](over-expression-u-sql.md) with the following restrictions: 
* The [ORDER BY](over-expression-u-sql.md#OBC) clause in the [OVER](over-expression-u-sql.md) operator is required. 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  

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

**A.    Compare values between years**   
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
TO "/Output/ReferenceGuide/Analytic/lead/exampleA.csv"
ORDER BY SalesYear DESC
USING Outputters.Csv();
```

**B.    Dividing the result set using PARTITION BY**   
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
TO "/Output/ReferenceGuide/Analytic/lead/exampleB.csv"
ORDER BY Region, Sales DESC
USING Outputters.Csv();
```

### See Also 
* [LAG (U-SQL)](lag-u-sql.md)
* [FIRST_VALUE (U-SQL)](first-value-u-sql.md)
* [LAST_VALUE (U-SQL)](last-value-u-sql.md)
* [Analytic Functions (U-SQL)](analytic-functions-u-sql.md)  
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 

