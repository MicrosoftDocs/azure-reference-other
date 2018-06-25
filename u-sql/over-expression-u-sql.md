---
title: "OVER Expression (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 04a87949-3ff3-491e-af75-4927a000ac63
caps.latest.revision: 26
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# OVER Expression (U-SQL)
A windowing expression is an expression whose value is computed by applying for every row a window function to multiple row values of a column (the window defined by the `OVER` operator) instead of just the column’s value of the row.  

> [!NOTE]  
> The `OVER` expression is sometimes referred to as an `OVER` Clause to make it search discoverable.

The `OVER` operator allows to specify a partition or window of column data that the window functions operate on. The windows provide the ability to access data from previous rows without having to use a self-join and provide both cumulative and sliding windows. It thus provides the ability to compute aggregated values such as moving averages, cumulative aggregates, running totals, or a top N per group results. 

It is similar to aggregation over grouping but instead of grouping the whole rowset with [GROUP BY](group-by-and-having-clauses-u-sql.md) and then returning a single aggregated value for each group, the window defines a set of rows for a particular column in the [SELECT](select-clause-u-sql.md) clause that will be aggregated for each row. In the [GROUP BY](group-by-and-having-clauses-u-sql.md) case, the result will be a row per group, with windowing expressions, the number of rows returned by the [SELECT](select-clause-u-sql.md) will not be affected by the windows. 

Windowing expressions are only supported inside expressions in a SELECT FROM clause. More than one windowing expression can be used in a single query with a single [FROM](from-clause-u-sql.md) clause. The `OVER` operator for each function can differ in partitioning and ordering. 

A windowing expression can never be used if a [GROUP BY](group-by-and-having-clauses-u-sql.md) clause is present. 

## Syntax
<pre>
Windowing_Expression := 
    <a href="#WFC">Window_Function_Call</a> '<a href="#OVR">OVER</a>' '('
        [ <a href="#OPBC">Over_Partition_By_Clause</a> ]
        [ <a href="#OBC">Order_By_Clause</a> ]
        [ <a href="#row_cla">Row_Clause</a> ]
    ')'.
</pre>

## Semantics of Syntax Elements 
* <a name="WFC"></a>**`Window_Function_Call`**  
  The window function that is being applied to the window. 

  ### Syntax
  <pre>
  Window_Function_Call := 
      <a href="aggregate-functions-u-sql.md">Aggregate_Function_Call</a>
  |   <a href="analytic-functions-u-sql.md">Analytic_Function_Call</a>
  |   <a href="ranking-functions-u-sql.md">Ranking_Function_Call</a>.
  </pre>
 
  Window functions can be one of the following:
  * [Aggregate Functions](aggregate-functions-u-sql.md) such as [SUM](sum-u-sql.md) or [MAX](max-u-sql.md). 
  * [Analytic Functions](analytic-functions-u-sql.md) such as [FIRST_VALUE](first-value-u-sql.md) or [LAST_VALUE](last-value-u-sql.md). 
  * [Ranking Functions](ranking-functions-u-sql.md) such as [RANK](rank-u-sql.md) or [ROW_NUMBER](row-number-u-sql.md).  
   
  Aggregation functions applied to a window cannot be used with [DISTINCT](select-clause-u-sql.md#dist).  

* <a name="OVR"></a>**`OVER ( … )`**  
The `OVER` operator that specifies the window with the following components. Note that certain windowing functions have certain requirements with respect to the presence or absence of some if these components. These requirements are explained in the relevant section describing that function. 

* <a name="OPBC"></a>**`Over_Partition_By_Clause`**  
The `OVER` operator’s optional partition clause defines the window by partitioning the rowset. The window function is applied to each partition separately and computation restarts for each partition. 

  ### Syntax
  <pre>
  Over_Partition_By_Clause := 
      'PARTITION' 'BY' Expression_List.
  </pre>

  The data can be partitioned according to a list of scalar expressions. The result type of each of the expression has to return an equality comparable type or an error is raised. Most commonly, the partition expressions refer to the rowset’s columns (as specified by the [FROM](from-clause-u-sql.md) clause and not the columns from the [SELECT](select-clause-u-sql.md) clause). 

  If `PARTITION BY` is not specified, the function treats all rows of the query result set as a single group. 

* <a name="OBC"></a>**`Order_By_Clause`**  
  The `OVER` operator’s optional `ORDER BY` clause defines the order of the rows withing each of the windows.   

  ### Syntax
  <pre>
  Order_By_Clause := 
      'ORDER' 'BY' Sort_Item_Expression_List.<br />
  Sort_Item_Expression_List :=
      Sort_Item_Expression { ',' Sort_Item_Expression }.<br />
  Sort_Item_Expression :=
      expression [Sort_Direction].
  </pre>
 
  The syntax and semantics follows the normal `ORDER BY` clause. For window functions that depend on the order such as the [ranking functions](ranking-functions-u-sql.md), this order by clause specifies the logical order in which the window function calculation is performed.  

  If the `ORDER BY` clause is not specified, then the window is not ordered.  

  > [!IMPORTANT]   
  > The `ORDER BY` specification in an `OVER` clause for aggregate functions is allowed only when a `ROWS` subclause is also specified.   

* <a name="row_cla"></a>**`Row_Clause`**   
  The `OVER` operator’s optional `ROWS` clause further limits the rows within a partition by specifying fixed number of rows preceding or following the current row. Preceding and following rows are defined based on the ordering in the `ORDER BY` clause. Therefore, the `ROWS` clause requires that the `ORDER BY` clause be specified.  

  ### Syntax
  <pre>
  Row_Clause := 
      'ROWS' Window_Frame_Extent.
  </pre>

  If the `ROWS` clause is not specified but `ORDER BY` is specified, `ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW` is used as the default for the window frame.  

  The `ROWS` clause is incompatible with the `DISTINCT` aggregate option and an error is raised. 

  * **Window_Frame_Extent**  
    The window frame extent specifies the rows specifying a lower bound and an upper bound by either just specifying the preceding rows from the current row or providing a frame between two explicitly specified end points.

    ### Syntax
    <pre>
    Window_Frame_Extent := 
        Window_Frame_Preceding | Window_Frame_Between.
    </pre>
    
    For example, `ROWS BETWEEN 2 PRECEDING AND CURRENT ROW` means that the window of rows that the function operates on is three rows in size, starting with 2 rows preceding until and including the current row. 

    * **Window_Frame_Preceding**   
      Defines the window frame relative from the current row. Currently supported are:

      ### Syntax
      <pre>
      Window_Frame_Preceding := 
          'UNBOUNDED' 'PRECEDING'
      |   unsigned_integer_literal 'PRECEDING' 
      |   'CURRENT' 'ROW'.
      </pre>

      With the following semantics: 

      * **UNBOUNDED PRECEDING**  
        Specifies that the window starts at the first row of the partition. It can only be specified as the window starting point. 

      * **unsigned_integer_literal PRECEDING**   
        The nonnegative integer literal specifies the number of rows to precede the current row in the partition. If the value is larger than the available number of preceding rows in the partition, then the window starts at the first row of the partition. 

      * **CURRENT ROW**   
        Specifies that the window starts or ends at the current row. It can be specified as both a starting and ending point. 

    * **Window_Frame_Between**   
      Specifies the lower (starting) and upper (ending) boundary points of the window. 

      ### Syntax
      <pre>
      Window_Frame_Between :=  
          'BETWEEN' Window_Frame_Bound
          'AND' Window_Frame_Bound.<br />
      Window_Frame_Bound :=
          Window_Frame_Preceding
      |   Window_Frame_Following.
      </pre>

      The first frame bound specifies the lower, the second frame bound the upper boundary (inclusive). If the upper boundary is smaller than the lower boundary, an error is raised. Note that a frame can be all preceding or all following the current row. The frame bounds are specified as follows: 

      * **Window_Frame_Preceding**  
        Specifies that the frame starts or ends before the current row as above 

      * **Window_Frame_Following**  
        Specifies that the frame starts or ends following the current row:

        ### Syntax
        <pre>
        Window_Frame_Following :=  
            unsigned_integer_literal 'FOLLOWING' 
        |   'CURRENT' 'ROW'.
        </pre>

        With the following semantics: 
        * **unsigned_integer_literal FOLLOWING**   
          The nonnegative integer literal specifies the number of rows to follow the current row in the partition. If the value is larger than the available number of following rows in the partition, then last row of the partition is chosen as the boundary. 

        * **CURRENT ROW**   
          Specifies that the window boundary is at the current row.  

          > [!TIP]  
          > U-SQL does currently not support `UNBOUNDED FOLLOWING`. One can achieve the same result by inverting the ordering and use `UNBOUNDED PRECEDING` instead. 


## Key Points
* Grouping collapses input rows 
* With grouping, aggregation happens on the entire set of rows or what is specified by the `GROUP BY` clause  
* Windowing does not collapse rows 
* With windowing, aggregations happen on the window defined by the `OVER` clause – either all rows and the rows defined by the window 
* `OVER( )` – defines a window of all rows 
* `OVER( PARTITION BY X )` – defines a window on column X 

## Examples  
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The example(s) below are based on the dataset(s) defined below.  Ensure your execution includes the rowset variable(s).

**Dataset**    
```sql
@data = 
    SELECT * FROM 
        ( VALUES
        (1, 100, new DateTime(2017,01,01)),
        (1, 200, new DateTime(2017,02,01)),
        (1, 300, new DateTime(2017,03,01)),
        (1, 400, new DateTime(2017,04,01)),
        (2, 400, new DateTime(2017,01,01)),
        (2, 300, new DateTime(2017,02,01)),
        (2, 200, new DateTime(2017,03,01)),
        (2, 100, new DateTime(2017,04,01)),
        (3, 75,  new DateTime(2017,04,01))
        ) AS T(EmpID, Sales, SaleDate);
```
<br />


**Basic Syntax**   
The window is undefined, thus the total `Sales` from all records is returned.
```sql
@result = 
    SELECT *, SUM(Sales) OVER () AS allSalesTotal
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/QSE/SELECT/OVER/example1.txt"
USING Outputters.Tsv();
```
<br />


**Over_Partition_By_Clause**   
The window is defined by the `SaleDate`, thus the total `Sales` for each `SaleDate` is returned.
```sql
@result = 
    SELECT *, SUM(Sales) OVER (PARTITION BY SaleDate) AS totalSalesBySaleDate
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/QSE/SELECT/OVER/example2.txt"
USING Outputters.Tsv();
```
<br />


**Order_By_Clause**   
The window is undefined, thus the first `Sales` figure from all records is returned - ordered by `EmpID`.
```sql
@result = 
    SELECT *, FIRST_VALUE(Sales) OVER (ORDER BY EmpID) AS firstSale_orderByEmpID
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/QSE/SELECT/OVER/example3.txt"
USING Outputters.Tsv();
```
<br />


**Over_Partition_By_Clause and Order_By_Clause**   
The window is defined by the `SaleDate`, thus the first `Sales` figure from each window is returned - orderd by EmpID DESC.
```sql
@result = 
    SELECT *, FIRST_VALUE(Sales) OVER (PARTITION BY SaleDate ORDER BY EmpID DESC) AS firstSale_partitionBySaleDate_orderByEmpID
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/QSE/SELECT/OVER/example4.txt"
USING Outputters.Tsv();
```
<br />


**Row_Clause**   
For non-aggregate functions, if the `ROWS` clause is not specified but `ORDER BY` is specified, `ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW` is used as the default for the window frame.
```sql
@result =
    SELECT EmpID,
           SaleDate.ToShortDateString() AS SaleDate,
           Sales,
           FIRST_VALUE(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) AS wROWS, // equivalent to below
           FIRST_VALUE(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate) AS woROWS // equivalent to above

           // SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate) AS woROWS, // will fail as aggregate functions require ROWS when ORDER BY is used.
           // SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) AS wROWS // equivalent to above
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/QSE/SELECT/OVER/row_clause.txt"
USING Outputters.Tsv(outputHeader: true);
```
<br />


**Window_Frame_Preceding**   
```sql
@result =
SELECT EmpID, SaleDate.ToShortDateString() AS SaleDate, Sales, 
		// Window frame starts at the first row of the partition (current row + all prior rows)(running total)
		// For EmpID 1 and SaleDate 2017-03-01, result is computed from 100 + 200 + 300
		SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS UNBOUNDED PRECEDING) AS unboundedPreceding,

		// Window frame starts one row prior to the current row in the partition (current row + plus 1 prior row)
		// For EmpID 1 and SaleDate 2017-03-01, result is computed from 200 + 300
		SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS 1 PRECEDING) AS integerPreceding,

		// Window frame starts and ends at current row in the partition (current row)
		// For EmpID 1 and SaleDate 2017-03-01, result is computed from 300
		SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS CURRENT ROW) AS currentRow,
		SUM(Sales) OVER(PARTITION BY EmpID, SaleDate) AS currentRow2 // equivalent to above
FROM @data;

OUTPUT @result
TO "/ReferenceGuide/QSE/SELECT/OVER/rows_WFP.csv"
USING Outputters.Csv(outputHeader: true);
```
<br />


**Window_Frame_Preceding vs. Window_Frame_Between**    
When `ROWS` is specified and `Window_Frame_Preceding` is used for `Window_Frame_Extent`, the expression is
equivalent to `Window_Frame_Between` where the `Window_Frame_Preceding` specification is used for the window frame boundary starting point and `CURRENT ROW` is used for the boundary ending point.
```sql
@result =
SELECT EmpID, SaleDate.ToShortDateString() AS SaleDate, Sales, 
        SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS UNBOUNDED PRECEDING) AS unboundedPreceding,  // Window_Frame_Preceding
        SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) AS unboundedPreceding_WFB,	// Window_Frame_Between equivalent to above	
		
        SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS 1 PRECEDING) AS integerPreceding, // Window_Frame_Preceding
        SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND CURRENT ROW) AS integerPreceding_WFB, // Window_Frame_Between equivalent to above	
		
        SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS CURRENT ROW) AS currentRow, // Window_Frame_Preceding
        SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN CURRENT ROW AND CURRENT ROW) AS currentRow_WFB // Window_Frame_Between equivalent to above	
FROM @data;

OUTPUT @result
TO "/ReferenceGuide/QSE/SELECT/OVER/rows_WFP_WFB.csv"
USING Outputters.Csv(outputHeader: true);
```
<br />


**Window_Frame_Between**  
```sql
@result =
    SELECT EmpID,
           SaleDate.ToShortDateString() AS SaleDate,
           Sales,
           // Window frame starts at the first row of the partition and ends one row prior to the current row in the partition (all prior rows up to 1 prior row)
           // For EmpID 1 and SaleDate 2017-03-01, result is computed from 100 + 200
           SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN UNBOUNDED PRECEDING AND 1 PRECEDING) AS unboundedPreceding_integerPreceding,

           // Window frame starts at the first row of the partition and ends one row following the current row in the partition (all prior rows up to 1 following row)
           // For EmpID 1 and SaleDate 2017-03-01, result is computed from 100 + 200 + 300 + 400
           SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN UNBOUNDED PRECEDING AND 1 FOLLOWING) AS unboundedPreceding_integerFollowing,

           // **Most common use of ROWS, this expression produces a running total**
           // Window frame starts at the first row of the partition and ends at the current row in the partition (all prior rows up to current row; running total)
           // For EmpID 1 and SaleDate 2017-03-01, result is computed from 100 + 200 + 300
           SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) AS unboundedPreceding_currentRow,


           // Window frame starts at one row prior of the partition and ends at one row prior in the partition (1 prior row)
           // For EmpID 1 and SaleDate 2017-03-01, result is computed from 200
           SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND 1 PRECEDING) AS integerPreceding_integerPreceding,

           // Window frame starts at one row prior of the partition and ends at one row following in the partition (1 prior row up to 1 following row)
           // For EmpID 1 and SaleDate 2017-03-01, result is computed from 200 + 300 + 400
           SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING) AS integerPreceding_integerFollowing,

           // Window frame starts at one row prior of the partition and ends at at the current row in the partition (1 prior row up to current row)
           // For EmpID 1 and SaleDate 2017-03-01, result is computed from 200 + 300
           SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND CURRENT ROW) AS integerPreceding_currentRow,


           // Window frame starts at the current row in the partition and ends at one row following in the partition (current row up to 1 following row)
           // For EmpID 1 and SaleDate 2017-03-01, result is computed from 300 + 400
           SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN CURRENT ROW AND 1 FOLLOWING) AS currentRow_integerFollowing,

           // Window frame starts at the current row in the partition and ends at the current row in the partition (current row)
           // For EmpID 1 and SaleDate 2017-03-01, result is computed from 300 
           SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN CURRENT ROW AND CURRENT ROW) AS currentRow_currentRow,


           // Specified window ending point is before the window starting point.
           // SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 FOLLOWING AND 1 PRECEDING) AS integerFollowing_integerPreceding

           // Window frame starts at one row past the current row in the partition and ends at one row following the current row in the partition (1 following row)
           // For EmpID 1 and SaleDate 2017-03-01, result is computed from 400
           SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 FOLLOWING AND 1 FOLLOWING) AS integerFollowing_integerFollowing

           // Specified window ending point is before the window starting point.
           // SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 FOLLOWING AND CURRENT ROW) AS integerFollowing_currentRow
FROM @data;

OUTPUT @result
TO "/ReferenceGuide/QSE/SELECT/OVER/rows_WFB.csv"
USING Outputters.Csv(outputHeader: true);
```
<br />


**UNBOUNDED FOLLOWING equivalent**   
U-SQL does currently not support` UNBOUNDED FOLLOWING`. One can achieve the same result by inverting the ordering and use `UNBOUNDED PRECEDING` instead.
Here, the SaleDate ordering is inverted in the [OVER](over-expression-u-sql.md#OVR) clause and then reverted in the [OUTPUT](output-statement-u-sql.md) statement.
```sql
@result =
SELECT EmpID, SaleDate.ToShortDateString() AS SaleDate, Sales, 
	// For EmpID 1 and SaleDate 2017-02-01, result is computed from 100 + 200 + 300 + 400
    SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate DESC ROWS BETWEEN UNBOUNDED PRECEDING AND 1 FOLLOWING) AS integerPreceding_UnboundedFollowing_equiv,

	// For EmpID 1 and SaleDate 2017-02-01, result is computed from 300 + 400
    SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate DESC ROWS BETWEEN UNBOUNDED PRECEDING AND 1 PRECEDING) AS integerFollowing_UnboundedFollowing_equiv,

	// For EmpID 1 and SaleDate 2017-02-01, result is computed from 200 + 300 + 400
    SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate DESC ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) AS currentRow_UnboundedFollowing_equiv
FROM @data;

OUTPUT @result
TO "/ReferenceGuide/QSE/SELECT/OVER/UF_equiv.csv"
ORDER BY EmpID, SaleDate
USING Outputters.Csv(outputHeader: true);
```
<br />


**Additional Example**   
For each month, the sales figures are provided for that month, the prior and following month, and the three month total and average.
Note the use of [LAG](lag-u-sql.md) and [LEAD](lead-u-sql.md) over `ROWS` when retrieving a single record.
```sql
@result =
    SELECT EmpID,
           SaleDate.ToShortDateString() AS SaleDate,
           LAG(Sales, 1, 0) OVER(PARTITION BY EmpID ORDER BY SaleDate) AS priorSales,
           // SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND 1 PRECEDING) AS priorSales2,
           Sales AS currentSales,
           LEAD(Sales, 1, 0) OVER(PARTITION BY EmpID ORDER BY SaleDate) AS followingSales,
           // SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 FOLLOWING AND 1 FOLLOWING) AS followingSales2,
           SUM(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING) AS threeMonthTotal,
           AVG(Sales) OVER(PARTITION BY EmpID ORDER BY SaleDate ROWS BETWEEN 1 PRECEDING AND 1 FOLLOWING) AS threeMonthAvg
FROM @data;

OUTPUT @result
TO "/ReferenceGuide/QSE/SELECT/OVER/rows_WFB_example.csv"
USING Outputters.Csv(outputHeader: true);
```
<br />




## See also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)   
* [Analytic Functions (U-SQL)](analytic-functions-u-sql.md)  
* [Ranking Functions (U-SQL)](ranking-functions-u-sql.md)  
* [Using U-SQL window functions for Azure Data Lake Analytics jobs](https://azure.microsoft.com/documentation/articles/data-lake-analytics-use-window-functions/) 
