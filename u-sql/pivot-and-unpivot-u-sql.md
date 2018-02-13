---
title: "PIVOT and UNPIVOT (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "04/27/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 27632ba6-50ff-4349-8d0c-1145e604d6ab
caps.latest.revision: 10
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# PIVOT and UNPIVOT (U-SQL)
You can use the PIVOT and UNPIVOT relational operators to change a rowset  expression into another rowset. PIVOT rotates a rowset expression by turning the unique values from one column in the expression into multiple columns in the output, and performs aggregations where they are required on any remaining column values that are wanted in the final output. UNPIVOT performs the opposite operation to PIVOT by rotating columns of a rowset expression into column values.

The syntax for PIVOT provides is simpler and more readable than the syntax that may otherwise be specified in a complex series of SELECT statements.

<table><th align="left">Syntax</th><tr><td><pre>
Pivot_Expression :=                                                                                      
     <a href="#als_row">Aliased_Rowset</a> 'PIVOT' '(' 
       <a href="#agg_func_call">Aggregate_Function_Call</a> 'FOR' <a href="#col_ident">Column_Identifier</a> 'IN' '(' 
         expression <a href="#col_alias">Column_Alias</a> {','  expression <a href="#col_alias">Column_Alias</a> }
       ')'
     ')'.<br />       
Unpivot_Expression :=
     <a href="#als_row">Aliased_Rowset</a> 'UNPIVOT' [Null_Handling] '('
       <a href="#col_ident">Column_Identifier</a> 'FOR' <a href="#col_ident">Column_Identifier</a> 'IN' '(' 
          <a href="#col_ident">Column_Identifier</a> {',' <a href="#col_ident">Column_Identifier</a> }
       ')'
     ')'.<br />
Null_Handling :=
     ('INCLUDE' | 'EXCLUDE') 'NULLS'.
</pre></td></tr></table>


### Semantics of Syntax Elements    
- <a name="als_row"></a>**`Aliased_Rowset`**    
  Aliased rowsets are rowsets that may or may not need a table alias.
  <table><th>Syntax</th><tr><td><pre>
  Aliased_Rowset :=                                                                                   
       Rowset [Alias]
  |    Rowset_Expression Alias.
  </pre></td></tr></table>
  
  - **`Alias`**  
    The rowset alias gives a name to the rowset that can be used in the remainder of the PIVOT expression to refer to that specific rowset. It can be a [quoted or unquoted identifier](u-sql-identifiers.md):
    <table><th>Syntax</th><tr><td><pre>
    Alias :=                                                                                       
         'AS' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>. 
    </pre></td></tr></table>
          
  - **`Rowset`**  
    The simplest rowset sources are a rowset variable such as `@rowset` that has been defined in a previous statement of the script and a table that has been created in the account’s catalog:
    <table><th>Syntax</th><tr><td><pre>
    Rowset :=                                                                                      
         Rowset_Variable
    |    Identifier.
    </pre></td></tr></table>
 
    A table can be referenced either with its fully 3-part qualified name, within the current database context with a 2-part name, or within the current database and schema context with a single-part name. Optionally, a table alias can be provided for an input rowset variable or table which then can be used in the remainder of the PIVOT expression.  
        
    Providing a rowset alias is optional.  
  
  - **`Rowset_Expression Alias`**  
    U-SQL also provides the ability to query over nested [query expressions](query-statements-and-expressions-u-sql.md), [table-valued function calls](u-sql-select-selecting-from-a-function-call.md) or querying [external rowsets](u-sql-select-selecting-from-an-external-rowset.md). Follow the links for more details on each.
        
    In these cases, a rowset alias has to be provided and cannot be left out.
    <table><th>Syntax</th><tr><td><pre>
    Rowset_Expression :=                                                                           
         '(' <a href="query-statements-and-expressions-u-sql.md">Query_Expression</a> ')'
    |    <a href="u-sql-select-selecting-from-a-function-call.md">Function_Call</a>
    |    <a href="u-sql-select-selecting-from-an-external-rowset.md">External_Rowset_Expression</a>.
    </pre></td></tr></table>  

- <a name="agg_func_call"></a>**`Aggregate_Function_Call`**  
Is a system or user-defined aggregate function that accepts one or more inputs. The aggregate function should be invariant to null values. An aggregate function invariant to null values does not consider null values in the group while it is evaluating the aggregate value.  Note that the Aggregate_Function_Call cannot contain `DISTINCT` aggregations. 

- <a name="col_ident"></a>**`Column_Identifier`**  
  The PIVOT expression can refer to column identifiers either by providing the quoted or unquoted identifier of the column, or by prepending the rowset/table alias or rowset variable name to identify the rowset to which the column belongs.   
  <table><th>Syntax</th><tr><td><pre>
  Column_Identifier :=                                                                                
       [(Rowset_Variable | <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>) '.']
       <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
  </pre></td></tr></table>

- <a name="col_alias"></a>**`Column_Alias`**  
  The column alias gives a name to the column that can be used in the remainder of the PIVOT expression to refer to that specific column. It can be a [quoted or unquoted identifier](u-sql-identifiers.md):
  <table><th>Syntax</th><tr><td><pre>
  Column_Alias :=                                                                                     
       'AS' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
  </pre></td></tr></table>
    
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Basic PIVOT Example**<a name="pivot_basic"></a>   
The example below repros "Basic PIVOT Example" from [Using PIVOT and UNPIVOT](https://docs.microsoft.com/sql/t-sql/queries/from-using-pivot-and-unpivot) in SQL Server.  To execute the example with the same data set, simply bcp or copy and paste `DaysToManufacture` and `StandardCost` from AdventureWorks2014.Production.Product to a local text file.  The same data set appears in at least [AdventureWorks2016](https://www.microsoft.com/download/details.aspx?id=49502).  An alternative solution using MAP_GG can be viewed at [PIVOT and MAP_AGG](map-agg-u-sql.md#pivot_basic)
```sql
// Using a data file created from a bcp export
@products =
     EXTRACT DaysToManufacture  int,
             StandardCost       double
     FROM "/ReferenceGuide/bcp/Production_Product.bcp"
     USING Extractors.Tsv();

// optional
@output =
    SELECT DaysToManufacture,
           AVG(StandardCost) AS AverageCost
    FROM @products
    GROUP BY DaysToManufacture;  

OUTPUT @output 
TO "/ReferenceGuide/DML/FROM/PIVOT/output1.txt"
USING Outputters.Tsv(outputHeader:true);

// pivot results
@pivotedProducts =
    SELECT "AverageCost" AS Cost_Sorted_By_Production_Days,  *  
    FROM @products
      PIVOT (
           AVG(StandardCost) FOR DaysToManufacture IN (
           0 AS [0],
           1 AS [1],
           2 AS [2],
           3 AS [3],
           4 AS [4])
           )
      AS PivotedTable;

OUTPUT @pivotedProducts 
TO "/ReferenceGuide/DML/FROM/PIVOT/pivotBasic.txt"
USING Outputters.Tsv(outputHeader:true);

// unpivot results
@unpivotedProducts = 
  SELECT DaysToManufacture, StandardCost
  FROM @pivotedProducts
    UNPIVOT (StandardCost FOR DaysToManufacture IN (
       [0],
       [1],
       [2],
       [3],
       [4]
    )) AS UnpivotedTable1;

OUTPUT @unpivotedProducts
TO "/ReferenceGuide/DML/FROM/PIVOT/unpivotBasic1.txt"
USING Outputters.Tsv(outputHeader:true, quoting: false);
```

**Complex PIVOT Example**<a name="pivot_complex"></a>   
The example below repros "Complex PIVOT Example" from [Using PIVOT and UNPIVOT](https://docs.microsoft.com/sql/t-sql/queries/from-using-pivot-and-unpivot) in SQL Server.  To execute the example with the same data set, simply bcp or copy and paste `PurchaseOrderID`, `EmployeeID` and `VendorID ` from AdventureWorks2014.Purchasing.PurchaseOrderHeader to a local text file.  The same data set appears in at least [AdventureWorks2016](https://www.microsoft.com/download/details.aspx?id=49502).   An alternative solution using MAP_GG can be viewed at [PIVOT and MAP_AGG - Additional Example](map-agg-u-sql.md#pivot_complex).
```sql
// Using a data file created from a bcp export
@PurchaseOrderHeader =
     EXTRACT PurchaseOrderID  int,
             EmployeeID       int,
             VendorID         int
     FROM "/ReferenceGuide/bcp/PurchaseOrderHeader.bcp"
     USING Extractors.Tsv();

// optional, non-pivoted result set
@output =
    SELECT VendorID,
           EmployeeID,
           COUNT(PurchaseOrderID) AS PurchaseOrders
    FROM @PurchaseOrderHeader
    WHERE EmployeeID IN(250, 251, 256, 257, 260)
    GROUP BY VendorID, EmployeeID;

OUTPUT @output 
TO "/ReferenceGuide/DML/FROM/PIVOT/output2.txt"
ORDER BY VendorID
USING Outputters.Tsv(outputHeader:true);

// pivot results
@pivotedResults =
    SELECT *  
    FROM @PurchaseOrderHeader
      PIVOT (
           COUNT(PurchaseOrderID) FOR EmployeeID IN (
           250 AS Emp1,
           251 AS Emp2,
           256 AS Emp3,
           257 AS Emp4,
           260 AS Emp5)
           )
      AS PivotedTable;

OUTPUT @pivotedResults 
TO "/ReferenceGuide/DML/FROM/PIVOT/pivotComplex.txt"
USING Outputters.Tsv(outputHeader:true);
```

**Additional PIVOT Example**<a name="addl_exmple"></a>    
```sql
@data = SELECT * FROM (VALUES
   ("Beatles", "George Harrison", 1943, "acoustic guitar", 1),
   ("Beatles", "John Lennon",     1940, "acoustic guitar", 2),
   ("Beatles", "Paul McCartney",  1942, "bass guitar", 5),
   ("Beatles", "Ringo Starr",     1940, "drums", 3),   
   ("Rolling Stones", "Charlie Watts",  1941, "drums", 1), 
   ("Rolling Stones", "Keith Richards", 1943, "acoustic guitar", 5), 
   ("Rolling Stones", "Mick Jagger",    1943, "vocals", 7), 
   ("Rolling Stones", "Ronnie Wood",    1947, "bass guitar", 6),      
   ("Creedence Clearwater Revival", "Doug Clifford", 1945, "drums", 0),
   ("Creedence Clearwater Revival", "John Fogerty",  1945, "lead guitar", 4),  
   ("Creedence Clearwater Revival", "Stu Cook",      1945, "bass guitar", 0),
   ("Creedence Clearwater Revival", "Tom Fogerty",   1941, "rhythm guitar", 2),
   ("Eagles", "Don Henley",     1947, "drums", 4),
   ("Eagles", "Glenn Frey",     1948, "acoustic guitar", 3), 
   ("Eagles", "Joe Walsh",      1947, "lead guitar", 4), 
   ("Eagles", "Timothy Schmit", 1947, "bass guitar", 2), 
   ("Pink Floyd", "David Gilmour",  1946, "lead guitar", 8),
   ("Pink Floyd", "Nick Mason",     1944, "drums", 4),    
   ("Pink Floyd", "Richard Wright", 1943, "keyboards", 3),
   ("Pink Floyd", "Roger Watters",  1943, "bass guitar", 3),
   ("Pink Floyd", "Syd Barrett",    1946, "rhythm guitar", 0)     
) AS RockBands(Band, Musician, YearOfBirth, Instrument, Children);

@result1 =
    SELECT * 
    FROM @data
      PIVOT (ANY_VALUE(Children) FOR YearOfBirth IN (
           1940 AS y1940,
           1941 AS y1941,
           1942 AS y1942,
           1943 AS y1943,
           1944 AS y1944,
           1945 AS y1945,
           1946 AS y1946,
           1947 AS y1947,
           1948 AS y1948))
      AS PivotedTable;

@result2 =
    SELECT * FROM @data
      PIVOT (ANY_VALUE(Instrument) FOR Band IN (
           "Beatles" AS Beatles,
           "Rolling Stones" AS [Rolling Stones],
           "Creedence Clearwater Revival" AS [CCR],
           "Eagles" AS [Eagles],
           "Pink Floyd" AS [Pink Floyd]))
      AS PivotedTable1
      PIVOT (ANY_VALUE(Children) FOR YearOfBirth IN (
           1940 AS y0,
           1941 AS y1,
           1942 AS y2,
           1943 AS y3,
           1944 AS y4,
           1945 AS y5,
           1946 AS y6,
           1947 AS y7,
           1948 AS y8))
      AS PivotedTable2;

OUTPUT @result1 
TO "/Output/ReferenceGuide/DML/From/Pivot/Pivoted1.tsv"
USING Outputters.Tsv(outputHeader:true, nullEscape:"#null#");

OUTPUT @result2 
TO "/Output/ReferenceGuide/DML/From/Pivot/Pivoted2.tsv"
USING Outputters.Tsv(outputHeader:true, nullEscape:"#null#");
```

**Basic UNPIVOT Example**<a name="unpivot_basic"></a>   
This example uses UNPIVOT against the pivoted results created from [Basic PIVOT Example](#pivot_basic) above.
```sql
@pivotedProducts =
     EXTRACT Cost_Sorted_By_Production_Days string,
             [0] double?,
             [1] double?,
             [2] double?,
             [3] double?,
             [4] double?
     FROM "/ReferenceGuide/DML/FROM/PIVOT/pivotBasic.txt"
     USING Extractors.Tsv(skipFirstNRows:1);

// unpivot results
@unpivotedProducts = 
  SELECT DaysToManufacture, StandardCost
  FROM @pivotedProducts
    UNPIVOT (StandardCost FOR DaysToManufacture IN (
       [0],
       [1],
       [2],
       [3],
       [4]
    )) AS UnpivotedTable1;

OUTPUT @unpivotedProducts
TO "/ReferenceGuide/DML/FROM/PIVOT/unpivotBasic2.txt"
USING Outputters.Tsv(outputHeader:true, quoting: false);
```

**Complex UNPIVOT Example**<a name="unpivot_complex"></a>      
This example uses UNPIVOT against the pivoted results created from [Complex PIVOT Example](#pivot_complex) above.
```sql
@pivotedResults =
     EXTRACT VendorID int,
            Emp1 int,
            Emp2 int,
            Emp3 int,
            Emp4 int,
            Emp5 int
     FROM "/ReferenceGuide/DML/FROM/PIVOT/pivotComplex.txt"
     USING Extractors.Tsv(skipFirstNRows:1);

// unpivot results
@unpivotedResults = 
  SELECT VendorID, 
  (EmployeeID == "Emp1") ? "250" : 
      (EmployeeID == "Emp2") ? "251" : 
      (EmployeeID == "Emp3") ? "256" : 
      (EmployeeID == "Emp4") ? "257" : 
      (EmployeeID == "Emp5") ? "260" :  "0" AS EmployeeID,
  PurchaseOrders 
  FROM @pivotedResults
    UNPIVOT (PurchaseOrders FOR EmployeeID IN (     
       Emp1,
       Emp2,
       Emp3,
       Emp4,
       Emp5
    )) AS UnpivotedTable1;

OUTPUT @unpivotedResults
TO "/ReferenceGuide/DML/FROM/PIVOT/unpivotComplex1.txt"
USING Outputters.Tsv(outputHeader:true, quoting: false);
```

**Additional UNPIVOT Example**  
This example uses UNPIVOT against the pivoted results created from [Additional PIVOT Example](#addl_exmple) above.
```sql
@data =
  EXTRACT
    Musician string,
    [Beatles] string,
    [Rolling Stones] string,
    [Creedence Clearwater Revival] string,
    [Eagles] string,
    [Pink Floyd] string,
    [1940] int?,
    [1941] int?,
    [1942] int?,
    [1943] int?,
    [1944] int?,
    [1945] int?,
    [1946] int?,
    [1947] int?,     
    [1948] int?
  FROM  @"/Output/ReferenceGuide/DML/From/Pivot/Pivoted2.tsv"
  USING Extractors.Tsv(skipFirstNRows:1, nullEscape:"#null#");

@result = 
  SELECT * 
  FROM @data
    UNPIVOT (Instrument FOR Band IN (
       [Beatles],
       [Rolling Stones],
       [Creedence Clearwater Revival],
       [Eagles],
       [Pink Floyd]
    )) AS UnpivotedTable1
    UNPIVOT (Children FOR YearOfBirth IN (
       [1940],
       [1941],
       [1942],
       [1943],
       [1944],
       [1945],
       [1946],
       [1947],
       [1948]  
    )) AS UnpivotedTable2;

OUTPUT @result 
TO "/Output/ReferenceGuide/DML/From/Pivot/UnPivoted1.tsv"
ORDER BY Band, Musician ASC
USING Outputters.Tsv(outputHeader:true, nullEscape:"#null#");
```

**UNPIVOT and NULL handling**  
Compare the output from the two queries below:
```sql
@data = 
  SELECT * FROM (VALUES
                 ("Band1", "Musician1", "Instrument1", (int?)1,    (int?)null  ),
                 ("Band2", "Musician2", "Instrument2", (int?)null, (int?)null  ),
                 ("Band3", "Musician3", "Instrument3", (int?)null, (int?)3     )
                ) AS T(Band, Musician, Instrument, [1940], [1941]);

// using INCLUDE NULLS
@result = 
  SELECT Band, Musician, YearOfBirth, Instrument, Children 
  FROM @data
       UNPIVOT INCLUDE NULLS (Children FOR YearOfBirth IN([1940], [1941])) AS UnpivotedTable;

OUTPUT @result 
TO "/ReferenceGuide/DML/FROM/PIVOT/unpivotIncludeNulls.txt"
USING Outputters.Tsv(outputHeader:true);


// using EXCLUDE NULLS
@result = 
  SELECT Band, Musician, YearOfBirth, Instrument, Children 
  FROM @data
       UNPIVOT EXCLUDE NULLS (Children FOR YearOfBirth IN([1940], [1941])) AS UnpivotedTable;

OUTPUT @result 
TO "/ReferenceGuide/DML/FROM/PIVOT/unpivotExcludeNulls.txt"
USING Outputters.Tsv(outputHeader:true);
```

### See Also
* [FROM Clause (U-SQL)](from-clause-u-sql.md) 
* [MAP_AGG (U-SQL)](map-agg-u-sql.md) (alternative method to pivot results)
    
    
    
