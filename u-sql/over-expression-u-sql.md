---
title: "OVER Expression (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 04a87949-3ff3-491e-af75-4927a000ac63
caps.latest.revision: 26
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# OVER Expression (U-SQL)
A windowing expression is an expression whose value is computed by applying for every row a window function to multiple row values of a column (the window defined by the OVER operator) instead of just the column’s value of the row.  

> [!NOTE]
> The OVER expression is sometimes referred to as an OVER Clause to make it search discoverable.

The OVER operator allows to specify a partition or window of column data that the window functions operate on. The windows provide the ability to access data from previous rows without having to use a self-join and provide both cumulative and sliding windows. It thus provides the ability to compute aggregated values such as moving averages, cumulative aggregates, running totals, or a top N per group results. 

It is similar to aggregation over grouping but instead of grouping the whole rowset with [GROUP BY](../u-sql/group-by-and-having-clauses-u-sql.md) and then returning a single aggregated value for each group, the window defines a set of rows for a particular column in the [SELECT](../u-sql/select-clause-u-sql.md) clause that will be aggregated for each row. In the [GROUP BY](../u-sql/group-by-and-having-clauses-u-sql.md) case, the result will be a row per group, with windowing expressions, the number of rows returned by the [SELECT](../u-sql/select-clause-u-sql.md) will not be affected by the windows. 

Windowing expressions are only supported inside expressions in a SELECT FROM clause. More than one windowing expression can be used in a single query with a single [FROM](../u-sql/from-clause-u-sql.md) clause. The OVER operator for each function can differ in partitioning and ordering. 

A windowing expression can never be used if a [GROUP BY](../u-sql/group-by-and-having-clauses-u-sql.md) clause is present. 

<table><th align="left">Syntax</th><tr><td><pre>
Windowing_Expression :=                                                                                  
     <a href="#WFC">Window_Function_Call</a> '<a href="#OVR">OVER</a>' '('
          [ <a href="#OPBC">Over_Partition_By_Clause</a> ]
          [ <a href="#OBC">Order_By_Clause</a> ]
          [ <a href="#row_cla">Row_Clause</a> ]
     ')'.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="WFC"></a>**`Window_Function_Call`**  
  The window function that is being applied to the window. 

  <table><th>Syntax</th><tr><td><pre>
  Window_Function_Call :=                                                                             
        <a href="aggregate-functions-u-sql.md">Aggregate_Function_Call</a>
  |     <a href="analytic-functions-u-sql.md">Analytic_Function_Call</a>
  |     <a href="ranking-functions-u-sql.md">Ranking_Function_Call</a>.
  </pre></td></tr></table>
 
  Window functions can be one of the following:
  * [Aggregate Functions](../u-sql/aggregate-functions-u-sql.md) such as [SUM](../u-sql/sum-u-sql.md) or [MAX](../u-sql/max-u-sql.md). 
  * [Analytic Functions](../u-sql/analytic-functions-u-sql.md) such as [FIRST_VALUE](../u-sql/first-value-u-sql.md) or [LAST_VALUE](../u-sql/last-value-u-sql.md). 
  * [Ranking Functions](../u-sql/ranking-functions-u-sql.md) such as [RANK](../u-sql/rank-u-sql.md) or [ROW_NUMBER](../u-sql/row-number-u-sql.md).  
   
  Aggregation functions applied to a window cannot be used with [DISTINCT](../u-sql/select-clause-u-sql.md#dist).  

* <a name="OVR"></a>**`OVER ( … )`**  
The OVER operator that specifies the window with the following components. Note that certain windowing functions have certain requirements with respect to the presence or absence of some if these components. These requirements are explained in the relevant section describing that function. 

* <a name="OPBC"></a>**`Over_Partition_By_Clause`**  
The OVER operator’s optional partition clause defines the window by partitioning the rowset. The window function is applied to each partition separately and computation restarts for each partition. 

  <table><th>Syntax</th><tr><td><pre>
  Over_Partition_By_Clause :=                                                                         
       'PARTITION' 'BY' Expression_List.
  </pre></td></tr></table>

  The data can be partitioned according to a list of scalar expressions. The result type of each of the expression has to return an equality comparable type or an error is raised. Most commonly, the partition expressions refer to the rowset’s columns (as specified by the [FROM](../u-sql/from-clause-u-sql.md) clause and not the columns from the [SELECT](../u-sql/select-clause-u-sql.md) clause). 

  If PARTITION BY is not specified, the function treats all rows of the query result set as a single group. 

* <a name="OBC"></a>**`Order_By_Clause`**  
  The OVER operator’s optional ORDER BY clause defines the order of the rows withing each of the windows.   

  <table><th>Syntax</th><tr><td><pre>
  Order_By_Clause :=                                                                                  
       'ORDER' 'BY' Sort_Item_Expression_List.<br />
  Sort_Item_Expression_List :=
       Sort_Item_Expression { ',' Sort_Item_Expression }.<br />
  Sort_Item_Expression :=
       expression [Sort_Direction].
  </pre></td></tr></table>
 
  The syntax and semantics follows the normal ORDER BY clause. For window functions that depend on the order such as the [ranking functions](../u-sql/ranking-functions-u-sql.md), this order by clause specifies the logical order in which the window function calculation is performed.  

  If the ORDER BY clause is not specified, then the window is not ordered.  

* <a name="row_cla"></a>**`Row_Clause`**   
  The OVER operator’s optional ROWS clause further limits the rows within a partition by specifying fixed number of rows preceding or following the current row. Preceding and following rows are defined based on the ordering in the ORDER BY clause. Therefore, the ROWS clause requires that the ORDER BY clause be specified.  

  <table><th>Syntax</th><tr><td><pre>
  Row_Clause :=                                                                                       
       'ROWS' Window_Frame_Extent.
  </pre></td></tr></table>

   If the ROWS clause is not specified but ORDER BY is specified, ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW is used as the default for the window frame.  

  The ROWS clause is incompatible with the DISTINCT aggregate option and an error is raised. 

  * **Window_Frame_Extent**  
    The window frame extent specifies the rows specifying a lower bound and an upper bound by either just specifying the preceding rows from the current row or providing a frame between two explicitly specified end points.
    <table><th>Syntax</th><tr><td><pre>
    Window_Frame_Extent :=                                                                         
         Window_Frame_Preceding | Window_Frame_Between.
    </pre></td></tr></table>
    
    For example, ROWS BETWEEN 2 PRECEDING AND CURRENT ROW means that the window of rows that the function operates on is three rows in size, starting with 2 rows preceding until and including the current row. 

    * **Window_Frame_Preceding**   
      Defines the window frame relative from the current row. Currently supported are:
      <table><th>Syntax</th><tr><td><pre>
      Window_Frame_Preceding :=                                                                 
           'UNBOUNDED' 'PRECEDING'
      |    unsigned_integer_literal 'PRECEDING' 
      |    'CURRENT' 'ROW'.
      </pre></td></tr></table>

      With the following semantics: 

      * **UNBOUNDED PRECEDING**  
        Specifies that the window starts at the first row of the partition. It can only be specified as the window starting point. 

      * **unsigned_integer_literal PRECEDING**   
        The nonnegative integer literal specifies the number of rows to precede the current row in the partition. If the value is larger than the available number of preceding rows in the partition, then the window starts at the first row of the partition. 

      * **CURRENT ROW**   
        Specifies that the window starts or ends at the current row. It can be specified as both a starting and ending point. 

    * **Window_Frame_Between**   
      Specifies the lower (starting) and upper (ending) boundary points of the window. 
      <table><th>Syntax</th><tr><td><pre>
      Window_Frame_Between :=                                                                   
           'BETWEEN' Window_Frame_Bound
           'AND' Window_Frame_Bound.<br />
      Window_Frame_Bound :=
           Window_Frame_Preceding
      |    Window_Frame_Following.
      </pre></td></tr></table>

      The first frame bound specifies the lower, the second frame bound the upper boundary (inclusive). If the upper boundary is smaller than the lower boundary, an error is raised. Note that a frame can be all preceding or all following the current row. The frame bounds are specified as follows: 

      * **Window_Frame_Preceding**  
        Specifies that the frame starts or ends before the current row as above 

      * **Window_Frame_Following**  
        Specifies that the frame starts or ends following the current row:
        <table><th>Syntax</th><tr><td><pre>
        Window_Frame_Following :=                                                            
             unsigned_integer_literal 'FOLLOWING' 
        |    'CURRENT' 'ROW'.
        </pre></td></tr></table>

        With the following semantics: 
        * **unsigned_integer_literal FOLLOWING**   
          The nonnegative integer literal specifies the number of rows to follow the current row in the partition. If the value is larger than the available number of following rows in the partition, then last row of the partition is chosen as the boundary. 

        * **CURRENT ROW**   
          Specifies that the window boundary is at the current row.  

          > [!TIP]
          > U-SQL does currently not support UNBOUNDED FOLLOWING. One can achieve the same result by inverting the ordering and use UNBOUNDED PRECEDING instead. 


### Examples  
### Sample Data 
It contains two views that we will use for the sample data. 

- QueryLog     
To access this data use the code below.             
```
querylog = Demo.QueryLog();
```

data:

|Fruit|Quantity|Source| 
|------|---|---------| 
|Banana|300|Image| 
|Cherry|300|Image| 
|Durian|500|Image|
|Apple|100|Web|
|Fig|200|Web|
|Papay|200|Web|
|Avocado|300|Web|
|Cherry|400|Web|
|Durian|500|Web|

 - Employees     
 To access this data use the code below.            
```
employees = Demo.Employees();
```

data:     

|EmpID|EmpName|DeptName|DeptID|Salary|
|-----|-------|--------|------|------|
|1|Noah|Engineering|100|10000|
|2|Sophia|Engineering|100|20000|
|3|Liam|Engineering|100|30000|
|4|Emma|HR|200|10000|
|5|Jacob|HR|200|10000|     
|6|Olivia|HR|200|10000|
|7|Mason|Executive|300|50000|
|8|Ava|Marketing|400|15000|
|9|Ethan|Marketing|400|10000|

Now, let’s walk through windowing functions and aggregations. As we do this the answer to this question will be clear and we’ll also understand the conceptual difference of Windowing Functions from Grouping.     
```
data3 =         
    SELECT EmpName, SUM(Salary) OVER( ) As SalaryAllDepts        
    FROM employees; 
```

Note these things: 

* We are still doing a SUM() but it is modified by an OVER clause 
* The OVER clause is empty – there’s nothing between the parentheses  
* The OVER clause defines the “window” – in this case since it is empty the window is the entire set of rows 
* Thus you can read SUM(Salary) OVER () as “The sum of Salary across the window of rows” 

|EmpName|TotalAllDepts|
|-------|--------------------|
|Noah|165000|
|Sophia|165000|
|Liam|165000|
|Emma|165000|
|Jacob|165000|
|Olivia|165000|
|Mason|165000|
|Ava|165000|
|Ethan|165000| 

When we did the first SUM without any GROUP BY we received the correct total salary 165000. But grouping collapsed that into a single row. Here we see there are as many output rows as input rows.  More interestingly the 165000 value is clearly calculated in each row but to calculate it data from EVERY row was used.  

Another way of thinking about this is that each output row has knowledge of multiple input rows - in this all of the input rows. The “window” is all the rows. Now let’s try an OVER clause that contains something. In this case by using PARTITION BY DeptName our window is based on DeptName.     
```
data4 =         
    SELECT EmpName, DeptName, SUM(Salary) OVER( PARTITION BY DeptName ) AS SalaryByDept  
    FROM employees; 
```
result: 

|EmpName|DeptName|SalaryByDept:double|
|-------|--------|-------------------|
|Noah|Engineering|60000|
|Sophia|Engineering|60000|
|Liam|Engineering|60000|
|Mason|Executive|50000|
|Emma|HR|30000|
|Jacob|HR|30000|
|Olivia|HR|30000|
|Ava|Marketing|25000|
|Ethan|Marketing|25000| 

Again, notice that there are the same number of input rows as output rows. However now each row has a Department total - again this is the cause the window for SUM was defined on the DeptName. 
Key points 
* grouping collapses input rows 
* with grouping aggregation happens on the entire set of rows or what is specified by the GROUP BY clause  
* windowing does not collapse rows 
* with windowing aggregations happen on the window defined by the OVER clause – either all rows and the rows defined by the window 
* OVER( ) – defines a window of all rows 
* OVER( PARTITION BY X ) – defines a window on column X 

Now let’s calculate the percentage of salary devoted to each department form the total salary across all departments. We can’t mix Windowing Functions and GROUP BY in the same statement so we’ll build it up like this:     

```
a =         
    SELECT TOP 1 SUM(Salary) OVER( ) AS SalaryAllDepts        
    FROM employees;     

b =           
    SELECT DeptName, SUM(Salary) AS SalaryByDept         
    FROM employees         
    GROUP BY DeptName;     
    
c = 
    SELECT DeptName, SalaryByDept, SalaryAllDepts, (SalaryByDept/SalaryAllDepts) AS Percentage         
    FROM a CROSS JOIN b;
```
 result: 
 
|DeptName|SalaryByDept|SalaryAllDepts|Percentage|
|--------|-------------------|---------------------|-----------------|
|Engineering|60000|165000|0.363636363636364|
|Executive|50000|165000|0.303030303030303|
|HR|30000|165000|0.181818181818182|
|Marketing|25000|165000|0.151515151515152|

### See also 
* [Aggregate Functions (U-SQL)](../u-sql/aggregate-functions-u-sql.md)   
* [Analytic Functions (U-SQL)](../u-sql/analytic-functions-u-sql.md)  
* [Ranking Functions (U-SQL)](../u-sql/ranking-functions-u-sql.md)  
* [Using U-SQL window functions for Azure Data Lake Analytics jobs](https://azure.microsoft.com/documentation/articles/data-lake-analytics-use-window-functions/) 








