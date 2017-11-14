---
title: "REDUCE Expression (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-17"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 61b62a7e-ce15-435a-a96b-d00c50d91a75
caps.latest.revision: 29
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# REDUCE Expression (U-SQL)
U-SQL provides the ability to write custom rowset reducers in C# using the [user-defined operator](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-objects--udo) extensibility framework by implementing an `IReducer`.  See [U-SQL Programmability Guide: User-Defined Reducer](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-reducer) for more information.   
  
A reducer, unlike an aggregator that operates on columns and produces a scalar value, provides a way to implement custom grouping and aggregation on a rowset and returning a rowset.  
  
A reducer is being invoked with the `REDUCE` expression that provide the necessary information about both the input rowset, the grouping columns, the expected result schema as well as additional information that is useful for optimization.  
  
A reducer is invoked once per group and produces zero or one or multiple rows per group in return.   
  
A reducer provides limited optimization support, because an optimizer cannot reason about the procedural C# code defining the reducer. For example, it cannot push predicates through to earlier statements unless the column used in the predicate is marked as read only. Therefore, it is recommended to instead use a [user-defined aggregator](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-aggregates--udagg) or use the optional [READONLY](#ro_cla) or [REQUIRED](#req_cla) clauses.  
  
<table><th>Syntax</th><tr><td><pre>
Reduce_Expression :=                                                                                      
    'REDUCE' <a href="#inp_row">Input_Rowset</a>   
    [<a href="#presort">'PRESORT'</a> <a href="#ON">Identifier_List</a>] 
    ('<a href="#ALL">ALL</a>' | <a href="#ON">'ON' Identifier_List</a>) 
    <a href="#pro_cla">Produce_Clause</a>  
    [<a href="#ro_cla">Readonly_Clause</a>]  
    [<a href="#req_cla">Required_Clause</a>]
    <a href="#us_cla">USING_Clause</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements  
- <a name="inp_row"></a>**`Input_Rowset`**   
Specifies the input rowset that the reducer will operate on as either the reference to a rowset name or by a nested rowset expression:
  
  <table><th>Syntax</th><tr><td><pre>
Input_Rowset :=                                                                                     
    Rowset | Rowset_Expression.                                                 
</pre></td></tr></table>

  with the following semantics:
      
  - **`Rowset`**   
The two simplest rowset sources are a rowset variable such as `@rowset` that has been defined in a previous statement of the script or a table that has been created in the account’s catalog:

    <table><th>Syntax</th><tr><td><pre>
Rowset :=
<a></a>   Rowset_Variable | Identifier.                                                               <a></a>
    </pre></td></tr></table>

    A table can be referenced either with its fully qualified 3-part name, within the current database context with a 2-part name, or within the current database and schema context with a single-part name.   
  
  - **`Rowset_Expression`**   
U-SQL also provides the ability to reduce nested [query expressions](query-statements-and-expressions-u-sql.md), [table-valued function calls](table-valued-function-expression-u-sql.md) or [querying external rowsets](u-sql-select-selecting-from-an-external-rowset.md). Follow the links for more details on each.  

    <table><th>Syntax</th><tr><td><pre>
Rowset_Expression := 
<a></a>   '(' <a href="query-statements-and-expressions-u-sql.md">Query_Expression</a> ')'
|   <a href="table-valued-function-expression-u-sql.md">Function_Call</a>                                                                              <a></a>
|   <a href="u-sql-select-selecting-from-an-external-rowset.md">External_Rowset_Expression</a>.
    </pre></td></tr></table>
  
    The UDO programming model makes both the values and the schema of the input rowset available in the context of the reducer's implementation.   

- <a name="presort"></a>**`PRESORT`**     
The optional `PRESORT` clause guarantees the rows are ordered by the given identifier. 

- <a name="ALL"></a>**`ALL`**    
  The optional `ALL` indicates that the whole input rowset will become the group to be reduced. Similar to a `GROUP BY ALL`.  
    
- <a name="ON"></a>**`ON Identifier_List`**   
  This option specifies the list of columns that define the groups.  
  
  <table><th>Syntax</th><tr><td><pre>
Identifier_List :=                                                                                  
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>                                               
    {',' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>}.  
</pre></td></tr></table>  
    
  If the columns are not part of the input rowset’s columns or are not comparable, an error is raised.  
    
- <a name="pro_cla"></a>**`Produce_Clause`**   
  Specifies the rowset schema returned by the `REDUCE` expression. 
  <table><th>Syntax</th><tr><td><pre>
Produce_Clause :=                                                                                   
    'PRODUCE' Column_Definition_List.
</pre></td></tr></table>

  - **`Column_Definition_List`**  
This list defines the schema of the reducer.  The returned columns are defined as a pair of column names and column types:
    <table><th>Syntax</th><tr><td><pre>
Column_Definition_List :=
<a></a>     Column_Definition { ',' Column_Definition}.
<a></a>                                                                                               <a></a>
Column_Definition :=
<a></a>     <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> <a href="built-in-u-sql-types.md">Built_in_Type</a>.
    </pre></td></tr></table>
     
    Each column has an identifier that can be either a [quoted or unquoted identifier](u-sql-identifiers.md). A column is typed with one of the U-SQL types that the reducer supports.  
    
    The UDO programming model makes the specified rowset schema available to the implementation of the reducer. An error is raised if the reducer is producing a schema that is incompatible with the specified return schema.  
  
- <a name="ro_cla"></a>**`Readonly_Clause`**     
The optional `READONLY` clause can help the UDO programmer to write more efficient code. For more information on how the UDO programmer can take advantage of this hint, see the U-SQL C# Developer’s Guide.  
  
  The optional `READONLY` clause specifies the columns are read only for the reducer and will be passed through to the output using either the same name or the specified column name in parenthesis. Only columns in the reduce expression’s ON clause can be marked `READONLY`, otherwise the error `“E_CSC_USER_UDOREADONLYNOTKEYCOLUMN: Column '…' cannot be marked as READONLY”` is raised. 
  
  <table><th>Syntax</th><tr><td><pre>
Readonly_Clause :=                                                                                  
    'READONLY' Star_Or_Readonly_Column_List.<br />
Star_Or_Readonly_Column_List :=
    '*' | Readonly_Column_List.<br />
Readonly_Column_List :=
    Readonly_Column { ',' Readonly_Column }.<br />
Readonly_Column :=
    Column_Identifier [Output_Column_Dependency_Alias].<br />
Output_Column_Dependency_Alias :=
    '(' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> ')'.
</pre></td></tr></table>
  
- <a name="req_cla"></a>**`Required_Clause`**      
The optional `REQUIRED` clause can help the UDO programmer to write more efficient code. For more information on how the UDO programmer can take advantage of this hint, see the U-SQL C# Developer’s Guide.  
  
  The optional `REQUIRED` clause specifies that either all columns are required on input for the reducer (if specified with `*`) or the specified columns are required. If a specified column is followed by a list of columns in parenthesis, then the input column is only required if the columns in that list are referenced from the output.  
  
  <table><th>Syntax</th><tr><td><pre>
Required_Clause :=                                                                                  
    'REQUIRED' Star_Or_Required_Column_List.<br />
Star_Or_Required_Column_List :=  
    '*' | Required_Column_List.<br />
Required_Column_List :=  
    Required_Column { ',' Required_Column}.<br />
Required_Column :=  
    Column_Identifier [Required_Output_Column_Dependency_List].<br />
Required_Output_Column_Dependency_List :=  
    '(' Identifier_List ')'.  
</pre></td></tr></table>
    
- <a name="us_cla"></a>**`Using_Clause`**  
The `USING` clause specifies which reducer should be used to transform the input rowset.  
  
  <table><th>Syntax</th><tr><td><pre>
USING_Clause :=                                                                                     
    'USING' udo_expression.
</pre></td></tr></table>
  
  The `USING` clause takes a C# expression that returns an instance of `IReducer`. Users can write their own by implementing an `IReducer` (see [U-SQL Programmability Guide: User-Defined Reducer](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-reducer) for more detail on how to write your own reducer). Most commonly, the UDO expression is either the instantiation of a reducer class of the form  
  ```
  USING new MyNameSpace.MyReducer(parameter:"value")
  ```
  or the invocation of a factory method  
  ```
  USING MyNameSpace.MyReducerFactory(parameter:"value")
  ```
  
  where `parameter` is a parameter of the reducer.  
  
### Examples  
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- For simplicity, the example(s) with user-defined code make use of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) for assembly management.  The main advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically.  To use Assembly registration instead of Code-Behind, see [Using Assemblies: Code-Behind vs. Assembly Registration Walkthrough](extending-u-sql-expressions-with-user-code.md#usingAssemblies).

<a name="RangeReducer">**User-Defined Reducer - RangeReducer**</a>   
Example is a slightly modified version of the example given at [How do I combine overlapping ranges using U-SQL? Introducing U-SQL Reducer UDOs](https://blogs.msdn.microsoft.com/azuredatalake/2016/06/27/how-do-i-combine-overlapping-ranges-using-u-sql-introducing-u-sql-reducer-udos/) and [usql/Examples/RangeReducer/RangeReducer/](https://github.com/Azure/usql/tree/master/Examples/RangeReducer/RangeReducer). Please review the reducer article for details.   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.
```csharp
using Microsoft.Analytics.Interfaces;
using Microsoft.Analytics.Types.Sql;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace ReduceSample
{
    [SqlUserDefinedReducer(IsRecursive = true)]                                                                        // not sure if it can run recursive yet. Need to test with large data sets.
    public class RangeReducer : IReducer
    {
        public override IEnumerable<IRow> Reduce(IRowset input, IUpdatableRow output)
        {
            // Init aggregation values
            bool first_row_processed = false;
            var begin = DateTime.MaxValue; // Dummy value to make compiler happy
            var end = DateTime.MinValue; // Dummy value to make compiler happy

            // requires that the reducer is PRESORTED on begin and READONLY on the reduce key.
            foreach (var row in input.Rows)
            {
                // Initialize the first interval with the first row if i is 0
                if (!first_row_processed)
                {
                    first_row_processed = true; // mark that we handled the first row
                    begin = row.Get<DateTime>("begin");
                    end = row.Get<DateTime>("end");
                    // If the end is just a time and not a date, it can be earlier than the begin, indicating it is on the next day.
                    // This let's fix up the end to the next day in that case
                    if (end < begin) { end = end.AddDays(1); }
                }
                else
                {
                    var b = row.Get<DateTime>("begin");
                    var e = row.Get<DateTime>("end");
                    // fix up the date if end is earlier than begin
                    if (e < b) { e = e.AddDays(1); }

                    // if the begin is still inside the interval, increase the interval if it is longer
                    if (b <= end)
                    {
                        // if the new end time is later than the current, extend the interval
                        if (e > end) { end = e; }
                    }
                    else // output the previous interval and start a new one
                    {
                        output.Set<DateTime>("begin", begin);
                        output.Set<DateTime>("end", end);
                        yield return output.AsReadOnly();
                        begin = b; end = e;
                    } // if
                } // if
            } // foreach

            // now output the last interval
            output.Set<DateTime>("begin", begin);
            output.Set<DateTime>("end", end);
            yield return output.AsReadOnly();
        } // Reduce

    } // RangeReducer
} // ReduceSample
```

**Using User-Defined Reducer - RangeReducer**   
Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```U-SQL
// Dataset
@aLog = 
    SELECT * FROM 
        ( VALUES
        ("ABC", new DateTime(2017,01,01, 05, 00, 00),    new DateTime(2017,01,01, 06, 00, 00)),
        ("XYZ", new DateTime(2017,01,01, 05, 00, 00),    new DateTime(2017,01,01, 06, 00, 00)),
        ("ABC", new DateTime(2017,01,01, 08, 00, 00),    new DateTime(2017,01,01, 09, 00, 00)),
        ("ABC", new DateTime(2017,01,01, 08, 00, 00),    new DateTime(2017,01,01, 10, 00, 00)),
        ("ABC", new DateTime(2017,01,01, 10, 00, 00),    new DateTime(2017,01,01, 14, 00, 00)),
        ("ABC", new DateTime(2017,01,01, 07, 00, 00),    new DateTime(2017,01,01, 11, 00, 00)),
        ("ABC", new DateTime(2017,01,01, 09, 00, 00),    new DateTime(2017,01,01, 11, 00, 00)),
        ("ABC", new DateTime(2017,01,01, 11, 00, 00),    new DateTime(2017,01,01, 11, 30, 00)),
        ("FOO", new DateTime(2017,01,01, 23, 40, 00),    new DateTime(2017,01,01, 23, 59, 00)),
        ("FOO", new DateTime(2017,01,01, 23, 50, 00),    new DateTime(2017,01,02, 00, 40, 00))
        ) AS T(user, begin, end);

// Data as is
@results =
    SELECT user,
           String.Format("{0:t}", begin) AS StartTime,
           String.Format("{0:t}", end) AS EndTime
    FROM @aLog;

OUTPUT @results
TO "/ReferenceGuide/QSE/PrimaryRowsetExpressions/Reducer/RangeReducerA.csv"  
USING Outputters.Csv();


// Using Reducer
@results =
    REDUCE @aLog
    PRESORT begin
    ON user
    PRODUCE user string,
            begin DateTime,
            end  DateTime
    READONLY user
    REQUIRED begin, end
    USING new ReduceSample.RangeReducer();

// Some formatting
@results =
    SELECT user,
           String.Format("{0:t}", begin) AS StartTime,
           String.Format("{0:t}", end) AS EndTime
    FROM @results
    ORDER BY begin OFFSET 0 ROWS;

OUTPUT @results
TO "/ReferenceGuide/QSE/PrimaryRowsetExpressions/Reducer/RangeReducerB.csv"
USING Outputters.Csv();
```
---

<a name="SalesReducer">**User-Defined Reducer - SalesReducer**</a>    
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.
```csharp
using Microsoft.Analytics.Interfaces;
using Microsoft.Analytics.Types.Sql;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace ReferenceGuide_Examples
{
    [SqlUserDefinedReducer]
    public class SalesReducer : IReducer
    {
        public override IEnumerable<IRow> Reduce(IRowset input, IUpdatableRow output)
        {
            decimal SalesAmount;
            decimal TaxAmt;

            foreach (IRow row in input.Rows)
            {
                SalesAmount = row.Get<decimal>("SalesAmount");
                TaxAmt = row.Get<decimal>("TaxAmt");

                if (SalesAmount + TaxAmt > 1000m)
                {
                    yield return output.AsReadOnly();
                }
            }
        }
    }
}
```

**Using User-Defined Reducer - SalesReducer**   
Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```U-SQL
// Dataset
@sales = 
    SELECT * FROM 
        ( VALUES
        ("SO43659", 349, 5, 2024.99m, 162.00m),
        ("SO43660", 326, 5, 419.46m, 33.56m),
        ("SO43661", 300, 6, 809.76m, 64.78m),
        ("SO43662", 330, 6, 1258.38m, 100.67m),
        ("SO43663", 322, 4, 419.46m, 33.56m),
        ("SO43664", 345, 1, 2039.99m, 163.20m),
        ("SO43665", 220, 1, 40.37m, 3.23m),
        ("SO43666", 330, 4, 419.46m, 33.56m),
        ("SO43667", 219, 3, 17.10m, 1.37m),
        ("SO43668", 317, 6, 2624.38m, 209.95m)
        ) AS T(SalesOrderNumber, ProductKey, SalesTerritoryKey, SalesAmount, TaxAmt);

// Using reducer
@reducer =
    REDUCE @sales 
    ON SalesOrderNumber, ProductKey, SalesTerritoryKey, SalesAmount, TaxAmt
    PRODUCE SalesOrderNumber, 
            ProductKey, 
            SalesTerritoryKey,
            SalesAmount,
            TaxAmt
    READONLY * 
    REQUIRED SalesAmount, TaxAmt
    USING new ReferenceGuide_Examples.SalesReducer();

OUTPUT @reducer
TO "/ReferenceGuide/QSE/PrimaryRowsetExpressions/Reducer/SalesReducerC.csv"
USING Outputters.Csv(outputHeader: true);

// NOT using reducer
@result = 
    SELECT *
    FROM @sales 
    WHERE SalesAmount + TaxAmt > 1000m;

OUTPUT @result
TO "/ReferenceGuide/QSE/PrimaryRowsetExpressions/Reducer/SalesReducerD.csv"
USING Outputters.Csv(outputHeader: true);
```

**Reducer with ORDER BY and FETCH**   
The [ORDER BY clause with FETCH](order-by-and-offset-fetch-clause-u-sql.md) allows the selection of a limited number of rows based on the specified order.
This examples continues to use `SalesReducer` defined earlier.
```
// Same as previous example but only returns top 3 records ordered by SalesAmount
@reducer =
    REDUCE @sales
    PRESORT SalesOrderNumber
    ON SalesOrderNumber, ProductKey, SalesTerritoryKey, SalesAmount, TaxAmt
    PRODUCE SalesOrderNumber, 
            ProductKey, 
            SalesTerritoryKey,
            SalesAmount,
            TaxAmt
    READONLY * 
    REQUIRED SalesAmount, TaxAmt
    USING new ReferenceGuide_Examples.SalesReducer()
    ORDER BY SalesAmount DESC FETCH 3 ROWS;

OUTPUT @reducer
TO "/ReferenceGuide/QSE/PrimaryRowsetExpressions/Reducer/SalesReducer_fetch3.txt"
USING Outputters.Tsv(outputHeader: true);
```
  
### See Also 
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md) 
* [Output Statement (U-SQL)](output-statement-u-sql.md)  
* [U-SQL Programmability Guide: User-Defined Reducer](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-reducer)   
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)
* [How to register U-SQL Assemblies in your U-SQL Catalog](https://blogs.msdn.microsoft.com/azuredatalake/2016/08/26/how-to-register-u-sql-assemblies-in-your-u-sql-catalog/)



  
