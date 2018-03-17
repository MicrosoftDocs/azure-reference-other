---
title: "COMBINE Expression (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "10/17/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b4f684cb-1f61-4056-8bc8-3d490c50789d
caps.latest.revision: 28
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# COMBINE Expression (U-SQL)
U-SQL provides the ability to write custom rowset combiners in C# using the [user-defined operator](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-objects--udo) extensibility framework by implementing an `ICombiner`.  See [U-SQL Programmability Guide: User-Defined Combiner](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-combiner)
 for more information.
  
A combiner provides a way to implement custom join operators that are more complex than the standard U-SQL join expressions.  
  
[//]: # 'Add link to join section'  
  
A combiner is being invoked with the COMBINE expression that provide the necessary information about both the input rowsets, the join clause, the expected result schema as well as additional information.  
  
A combiner provides limited optimization support, because an optimizer cannot reason about the procedural C# code defining the combiner For example, it cannot not push predicates through to earlier statements unless the column used in the predicate is marked as read only. Therefore, it is recommended to instead use the standard [joins](u-sql-select-selecting-from-joins.md) if possible or use the [READONLY](#RO_cla) and [REQURED](#REQ_cla) clauses.  
 
<table><th align="left">Syntax</th><tr><td><pre>
Combine_Expression :=                                                                                    
    'COMBINE' <a href="#com_inp">Combine_Input</a>                            
    'WITH' <a href="#com_inp">Combine_Input</a>  
    <a href="#JOC">Join_On_Clause</a>  
    <a href="#pro_cla">Produce_Clause</a>                                 
    [<a href="#RO_cla">Readonly_Clause</a>]  
    [<a href="#REQ_cla">Required_Clause</a>]  
    <a href="#us_cla">Using_Clause</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements  
- <a name="com_inp"></a>**`Combine_Input`**  
Specifies the input rowsets that the combiner will join.  
  
  [//]: # 'ADD SOON: with an optional presort clause. [Presort_Clause]'  
  
  <table><th>Syntax</th><tr><td><pre>
  Combine_Input :=                                                                                    
      Aliased_Rowset.
  </pre></td></tr></table>
  
  with    
  
  - **`Aliased_Rowset`**   
  Aliased rowsets are rowsets that may or may not need a table alias.
    <table><th>Syntax</th><tr><td><pre>
    Aliased_Rowset :=                                                                              
        Rowset [Alias] | Rowset_Expression Alias.</pre></td></tr></table>
 
    where 
    
    - **`Alias`**
      is the rowset alias given to the rowset that can be used in the remainder of the `COMBINE` expression to refer to that specific rowset. It can be a [quoted or unquoted identifier](u-sql-identifiers.md):
      <table><th>Syntax</th><tr><td><pre>
      Alias :=                                                                                  
          'AS' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
      </pre></td></tr></table>

    - **`Rowset`**   
      The two simplest rowset sources are a rowset variable such as `@rowset` that has been defined in a previous statement of the script or a table that has been created in the account’s catalog:
      <table><th>Syntax</th><tr><td><pre>
      Rowset :=                                                                                 
          Rowset_Variable | Identifier.
      </pre></td></tr></table>
  
      A table can be referenced either with its fully qualified 3-part name, within the current database context with a 2-part name, or within the current database and schema context with a single-part name. Optionally, a table alias can be provided for an input rowset variable or table which then can be used in the remainder of the `COMBINE` expression.   
      
      Providing a rowset alias is optional.  
        
    - **`Rowset_Expression`**  
      U-SQL also provides the ability to combine nested [query expressions](query-statements-and-expressions-u-sql.md), [table-valued function calls](table-valued-function-expression-u-sql.md) or [querying external rowsets](u-sql-select-selecting-from-an-external-rowset.md). Follow the links for more details on each.

      <table><th>Syntax</th><tr><td><pre>
      Rowset_Expression :=                                                                      
          '(' <a href="query-statements-and-expressions-u-sql.md">Query_Expression</a> ')' 
      |   <a href="table-valued-function-expression-u-sql.md">Function_Call</a>
      |   <a href="u-sql-select-selecting-from-an-external-rowset.md">External_Rowset_Expression</a>.
      </pre></td></tr></table>
 
      In these cases, a rowset alias has to be provided and cannot be left out.    
      The UDO programming model makes both the values and the schema of the input rowsets available in the context of the combiner's implementation.   
        
[//]: # '•  Presort_Clause  
Content is under development and will be provided soon.  
Presort_Clause := \'PRESORT\' Sort_Item_List.'  
  
- <a name="JOC"></a>**`Join_On_Clause`**  
Specifies the join comparison that is being used to identify which of the rows from each rowset will be joined.

  <table><th>Syntax</th><tr><td><pre>
  Join_On_Clause :=                                                                                   
      'ON' <a href="u-sql-select-selecting-from-joins.md#joinComps">Join_Comparison_Expression</a>.</pre></td></tr></table> 
  
  where [`Join_Comparison_Expression`](u-sql-select-selecting-from-joins.md#joinComps) provides the join comparison expression for the combiner.   
  
- <a name="pro_cla"></a>**`Produce_Clause`**    
Specifies the rowset schema returned by the COMBINE expression.

  <table><th>Syntax</th><tr><td><pre>
  Produce_Clause :=                                                                                   
      'PRODUCE' Column_Definition_List.</pre></td></tr></table>
  
  where  
    
  - **`Column_Definition_List`**  
    This list defines the schema of the combiner.  The returned columns are defined as a pair of column names and column types:
    <table><th>Syntax</th><tr><td><pre>
    Column_Definition_List :=                                                                      
         Column_Definition { ',' Column_Definition}.<br />     
    Column_Definition :=
         <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> <a href="built-in-u-sql-types.md">Built_in_Type</a>.</pre></td></tr></table>

    Each column has an identifier that can be either a [quoted or unquoted identifier](u-sql-identifiers.md). A column is typed with one of the [U-SQL types](data-types-and-literals-u-sql.md) that the combiner supports.  
    
    The UDO programming model makes the specified rowset schema available to the implementation of the combiner. An error is raised if the combiner is producing a schema that is incompatible with the specified return schema.  
    
- <a name="RO_cla"></a>**`Readonly_Clause`**    
  The optional `READONLY` clause can help the UDO programmer to write more efficient code. For more information on how the UDO programmer can take advantage of this hint, see the U-SQL C# Developer’s Guide.  
  
  The optional `READONLY` clause specifies the columns are read only for the combiner and will be passed through to the output using either the same name or the specified column name in parenthesis. Only columns in the combine expression’s ON clause can be marked `READONLY`, otherwise the error `“E_CSC_USER_UDOREADONLYNOTKEYCOLUMN: Column '…' cannot be marked as READONLY”` is raised.
  
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
      '(' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> ')'.</pre></td></tr></table>  
      
- <a name="REQ_cla"></a>**`Required_Clause`**    
  The optional `REQUIRED` clause can help the UDO programmer to write more efficient code. For more information on how the UDO programmer can take advantage of this hint, see the U-SQL C# Developer’s Guide.  
  
  The optional `REQUIRED` clause specifies that either all columns are required on input for the combiner (if specified with `*`) or the specified columns are required. If a specified column is followed by a list of columns in parenthesis, then the input column is only required if the columns in that list are referenced from the output.  
  
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
      '(' Identifier_List ')'.</pre></td></tr></table> 
      
- <a name="us_cla"></a>**`Using_Clause`**   
  The `USING` clause specifies which combiner should be used to transform the input rowset.  

  <table><th>Syntax</th><tr><td><pre>
  USING_Clause :=                                                                                     
      'USING' udo_expression.</pre></td></tr></table>
 
  The `USING` clause takes a C# expression that returns an instance of `ICombiner`. Users can write their own by implementing an `ICombiner` (see [U-SQL Programmability Guide: User-Defined Combiner](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-combiner) for more detail on how to write your own combiner). Most commonly, the UDO expression is either the instantiation of a combiner class of the form  
  ```
  USING new MyNameSpace.MyCombiner(parameter:"value")
  ```
  or the invocation of a factory method  
  ```
  USING MyNameSpace.MyCombinerFactory(parameter:"value")
  ```
  
  where `parameter` is a parameter of the combiner.  
  
### Example
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script can be executed [locally](https://channel9.msdn.com/Series/AzureDataLake/USQL-LocalRun).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- For simplicity, the example(s) with user-defined code make use of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) for assembly management.  The main advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically.  To use Assembly registration instead of Code-Behind, see [Using Assemblies: Code-Behind vs. Assembly Registration Walkthrough](extending-u-sql-expressions-with-user-code.md#usingAssemblies).

**<a name="combinerEX">User-Defined Combiner - CombinerEX**</a>       
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
    [SqlUserDefinedCombiner]
    public class CombinerEX : ICombiner
    {
        public override IEnumerable<IRow> Combine(IRowset left, IRowset right, IUpdatableRow output)
        {
            var theRight = (from row in right.Rows
                            select new
                            {
                                Division = row.Get<string>("Division"),
                                carIDstart = row.Get<int>("carIDstart"),
                                carIDend = row.Get<int>("carIDend")
                            }).ToList();

            foreach (var row in left.Rows)
            {
                int carID = row.Get<int>("carID");

                var theLeft = (from w in theRight
                               where carID >= w.carIDstart && carID <= w.carIDend
                               select new
                               {
                                   Division = w.Division
                               }).ToList();

                output.Set<string>("currentModel", row.Get<string>("currentModel"));
                output.Set<string>("introYear", row.Get<string>("introYear"));
                output.Set<string>("Division", theLeft[0].Division);
                yield return output.AsReadOnly();
            }
        }
    }
}
```

**Using User-Defined Combiner - CombinerEX**  
Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```sql
@right = 
    SELECT * FROM 
        ( VALUES
        (0, 99, "Ford Motor Company", "Ford"),
        (100, 199, "Ford Motor Company", "Lincoln"),
        (200, 299, "Ford Motor Company", "Motorcraft"),
        (300, 399, "General Motors Company", "Buick"),
        (400, 499, "General Motors Company", "Chevrolet"),
        (500, 599, "General Motors Company", "Cadillac"),
        (600, 699, "General Motors Company", "GMC"),
        (700, 799, "Fiat Chrysler", "Chrysler"),
        (800, 899, "Fiat Chrysler", "Dodge"),
        (900, 999, "Fiat Chrysler", "Jeep"),
        (1000, 1099, "Fiat Chrysler", "Ram"),
        (1100, 1199, "Fiat Chrysler", "Mopar"),
        (1200, 1299, "Fiat Chrysler", "SRT")
        ) AS T(carIDstart, carIDend, Automaker, Division);

@left = 
    SELECT * FROM 
        ( VALUES
        (3, 0, "Mustang", "1964"),
        (7, 0, "Fiesta", "1976"),
        (133, 100, "Navigator", "1998"),
        (160, 100, "Continental", "2017"),
        (639, 600, "Canyon", "2004"),
        (801, 800, "Challenger", "2008"),
        (802, 800, "Charger", "2006")
        ) AS T(carID, baseID, currentModel, introYear);

@result =
    COMBINE @left AS l
    WITH @right AS r
    ON l.baseID == r.carIDstart
    PRODUCE currentModel string,
            Division string,
            introYear string
    REQUIRED Division, carIDstart, carIDend, carID, currentModel, introYear
    USING new ReferenceGuide_Examples.CombinerEX();

OUTPUT @result
TO "/ReferenceGuide/QSE/PrimaryRowsetExpressions/Combine/ExampleA.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Combiner with ORDER BY and FETCH**   
The [ORDER BY clause with FETCH](order-by-and-offset-fetch-clause-u-sql.md) allows the selection of a limited number of rows based on the specified order.
This examples continues to use `CombinerEX` defined above.

```sql
// Same as previous example but only returns top 3 records ordered by introYear
@result =
    COMBINE @left AS l
    WITH @right AS r
    ON l.baseID == r.carIDstart
    PRODUCE currentModel string,
            Division string,
            introYear string            
    REQUIRED Division, carIDstart, carIDend, carID, currentModel, introYear
    USING new ReferenceGuide_Examples.CombinerEX()
    ORDER BY introYear DESC FETCH 3 ROWS;

    OUTPUT @result
    TO "/ReferenceGuide/QSE/PrimaryRowsetExpressions/Combine/ExampleB.txt"
    USING Outputters.Tsv(outputHeader: true);
```

### See Also 
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md)  
* [Output Statement (U-SQL)](output-statement-u-sql.md)  
* [U-SQL Programmability Guide: User-Defined Combiner](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-combiner)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md) 
* [How to register U-SQL Assemblies in your U-SQL Catalog](https://blogs.msdn.microsoft.com/azuredatalake/2016/08/26/how-to-register-u-sql-assemblies-in-your-u-sql-catalog/)



