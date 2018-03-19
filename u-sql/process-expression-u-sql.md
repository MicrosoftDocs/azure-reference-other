---
title: "PROCESS Expression (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "10/17/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 39277bfa-0984-471f-b628-9d4eeb6f9a21
caps.latest.revision: 29
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# PROCESS Expression (U-SQL)
U-SQL provides the ability to write custom rowset processors in C# using the [user-defined operator](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-objects--udo) extensibility framework by implementing an `IProcessor`.  For more information, see [U-SQL Programmability Guide: User-Defined Processor](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-processor).
   
A processor is being invoked with the `PROCESS` expression that provides the necessary information about the input rowset, the expected result schema as well as additional information that is useful for optimization.  
  
A processor operates on a row at a time and produces zero or one row. If the processing should produce multiple rows per input, an [Applier](u-sql-using-apply-with-an-applier-udo.md) should be used instead.  
  
Some common applications of processors are to normalize nested data into relational form, modify values, or generate new columns using existing columns.   
  
Processors' strengths are in the context of performing complex C# processing where the processing depends on either the input or output schema, or when additional resources need to be accessed. Basically any tasks that are not easily accomplished with [user-defined functions](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-functions---udf) in the [SELECT](select-clause-u-sql.md) clause.  
  
A processor provides limited optimization support, because an optimizer cannot reason about the procedural C# code defining the processor. For example, it cannot push predicates through to earlier statements unless the column used in the predicate is marked as read only. Therefore, it is recommended to instead use [user-defined functions](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-functions---udf) and put the logic into the [SELECT](select-clause-u-sql.md) clause and [WHERE](where-clause-u-sql.md) clause of a [SELECT](select-expression-u-sql.md) expression if possible.   
  
<table><th align="left">Syntax</th><tr><td><pre>
Process_Expression :=                                                                                    
    'PROCESS' <a href="#inp_row">Input_Rowset</a>  
    <a href="#pro_cla">Produce_Clause</a>  
    [<a href="#RO_cla">Readonly_Clause</a>]  
    [<a href="#REQ_cla">Required_Clause</a>]                                    
    <a href="#USE_cla">Using_Clause</a>.  
</pre></td></tr></table>
  
### Semantics of Syntax Elements  
- <a name="inp_row"></a>**`Input_Rowset`**  
  Specifies the input rowset that the processor will operate on as either the reference to a rowset name or by a nested rowset expression:
  <table><th>Syntax</th><tr><td><pre>
  Input_Rowset :=                                                                                     
      <a href="#rowset">Rowset</a> | <a href="#rowset_exp">Rowset_Expression</a>.</pre></td></tr></table>    

  with the following semantics:  
  
  - <a name="rowset"></a>**`Rowset`**  
    The two simplest rowset sources are a rowset variable such as `@rowset` that has been defined in a previous statement of the script, or a table that has been created in the account’s catalog:

    <table><th>Syntax</th><tr><td><pre>
    Rowset :=                                                                                      
        Rowset_Variable | Identifier.</pre></td></tr></table>

    A table can be referenced either with its fully qualified 3-part name, within the current database context with a 2-part name, or within the current database and schema context with a single-part name.   
  
  - <a name="rowset_exp"></a>**`Rowset_Expression`**  
    U-SQL also provides the ability to process nested [query expressions](query-statements-and-expressions-u-sql.md), [table-valued function calls](u-sql-select-selecting-from-a-function-call.md) or [querying external rowsets](u-sql-select-selecting-from-an-external-rowset.md). Follow the links for more details on each.

    <table><th>Syntax</th><tr><td><pre>
    Rowset_Expression :=                                                                           
        '(' <a href="query-statements-and-expressions-u-sql.md">Query_Expression</a> ')'
    |   <a href="u-sql-select-selecting-from-a-function-call.md">Function_Call</a>
    |   <a href="u-sql-select-selecting-from-an-external-rowset.md">External_Rowset_Expression</a>.
    </pre></td></tr></table>
  
     The UDO programming model makes both the values and the schema of the input rowset available in the context of the processor's implementation.   
      
- <a name="pro_cla"></a>**`Produce_Clause`**   
  Specifies the rowset schema returned by the `PROCESS` expression.   
  <table><th>Syntax</th><tr><td><pre>
  Produce_Clause :=                                                                                   
      'PRODUCE' Column_Definition_List.</pre></td></tr></table>  
  
  - **`Column_Definition_List`**  
    This list defines the schema of the processor.  The returned columns are defined as a pair of column names and column types:
  
    <table><th>Syntax</th><tr><td><pre>
    Column_Definition_List :=                                                                      
        Column_Definition { ',' Column_Definition}.<br />
    Column_Definition :=
        <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> <a href="built-in-u-sql-types.md">Built_in_Type</a>.</pre></td></tr></table>
      
    Each column has an identifier that can be either a [quoted or unquoted identifier](u-sql-identifiers.md). A column is typed with one of the U-SQL types that the processor supports.  
    
    The UDO programming model makes the specified rowset schema available to the implementation of the processor. An error is raised if the processor is producing a schema that is incompatible with the specified return schema.  
    
- <a name="RO_cla"></a>**`Readonly_Clause`**   
  The optional `READONLY` clause can help the UDO programmer to write more efficient code. For more information on how the UDO programmer can take advantage of this hint, see the U-SQL C# Developer’s Guide.  
  
  The optional `READONLY` clause specifies that either all columns (if specified with `*`) or the specified columns are read only for the processor and will be passed through to the output using either the same name or the specified column name in parenthesis.
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
  
  The optional `REQUIRED` clause specifies that either all columns are required on input for the processor (if specified with `*`) or the specified columns are required. If a specified column is followed by a list of columns in parenthesis, then the input column is only required if the columns in that list are referenced from the output.
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
      
- <a name="USE_cla"></a>**`Using_Clause`**   
  The `USING` clause specifies which processor should be used to transform the input rowset.
  <table><th>Syntax</th><tr><td><pre>
  USING_Clause :=                                                                                     
      'USING' udo_expression.</pre></td></tr></table>
  
  The `USING` clause takes a C# expression that returns an instance of `IProcessor`. Users can write their own by implementing an `IProcessor` (see [U-SQL Programmability Guide: User-Defined Processor](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-processor) for more details on how to write your own processor). Most commonly, the UDO expression is either the instantiation of a processor class of the form    
  ```sql
  USING new MyNameSpace.MyProcessor(parameter:"value")                          
  ```
  or the invocation of a factory method  
  ```sql
  USING MyNameSpace.MyProcessorFactory(parameter:"value")                       
  ```
  
  where `parameter` is a parameter of the processor.  
  
### Examples    
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://channel9.msdn.com/Series/AzureDataLake/USQL-LocalRun).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- For simplicity, the example(s) with user-defined code make use of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) for assembly management.  The main advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically.  To use Assembly registration instead of Code-Behind, see [Using Assemblies: Code-Behind vs. Assembly Registration Walkthrough](extending-u-sql-expressions-with-user-code.md#usingAssemblies).

<a name="FullAddressProcessor">**User-Defined Processor - FullAddressProcessor**</a>   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.

```csharp
using Microsoft.Analytics.Interfaces;
using Microsoft.Analytics.Types.Sql;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;

namespace ReferenceGuide_Examples
{
    [SqlUserDefinedProcessor]
    public class FullAddressProcessor : IProcessor
    {
        public override IRow Process(IRow input, IUpdatableRow output)
        {
            string streetAddress = input.Get<string>("streetAddress");
            string city = input.Get<string>("city");
            string zipCode = input.Get<string>("zipCode");
            string country = input.Get<string>("country");
            string full_address = streetAddress + ", " + city + ", " + zipCode + " " + country;
            output.Set<string>("full_address", full_address);
            output.Set<Guid>("new_guid", Guid.NewGuid());
            return output.AsReadOnly();
        }
    }
}
``` 

**Using User-Defined Processor - FullAddressProcessor**  
The processor generates a new column "full_address" by combining streetAddress, city, zipCode, and country. It also generates a new guid.  Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```sql
// Dataset
@employees = 
    SELECT * FROM 
        ( VALUES
        (new Guid("c8fc966a-6144-4054-9170-6f05ff240812"), "Maria Anders", "Obere Str. 57", "Berlin", "12209", "Germany", "cell:030-0074321,office:030-0076545"),
        (new Guid("9499718f-1c21-4b78-84e7-3868a7fab280"), "Thomas Hardy", "120 Hanover Sq.", "London", "WA1 1DP", "UK","cell:(171) 555-7788,office:(171) 555-6750"),
        (new Guid("e1f04df2-b391-4a6c-a66a-9360626f3cdb"), "Elizabeth Lincoln", "23 Tsawassen Blvd.", "Tsawassen BC", "T2F 8M4", "Canada", "cell:(604) 555-4729,office:(604) 555-3745"),
        (new Guid("5609618a-a77a-4230-bae1-aee126b0f0ac"), "Patricio Simpson", "Cerrito 333", "Buenos Aires", "1010", "Argentina", "cell:(1) 135-5555,office:(1) 135-4892"),
        (new Guid("7ee97a9d-b00b-4b47-8846-020c53ec6f24"), "Yang Wang", "Hauptstr. 29", "Bern", "3012", "Switzerland", "cell:0452-076545")
        ) AS T(guid, Driver, streetAddress, city, zipCode, country, phoneNumbers);

// Data as is
OUTPUT @employees
TO "/ReferenceGuide/QSE/PrimaryRowsetExpressions/Process/FullAddressProcessorA.csv"
USING Outputters.Csv();

// Using processor
@results =
     PROCESS @employees
     PRODUCE new_guid Guid,
             Driver,
             full_address string,
             phoneNumbers
     READONLY Driver, phoneNumbers
     REQUIRED streetAddress, city, zipCode, country
     USING new ReferenceGuide_Examples.FullAddressProcessor ();

OUTPUT @results
TO "/ReferenceGuide/QSE/PrimaryRowsetExpressions/Process/FullAddressProcessorB.csv"
USING Outputters.Csv();
```
---

<a name="CountryName">**User-Defined Processor - CountryName**</a>   
This is a modified example from [Develop U-SQL user-defined operators for Azure Data Lake Analytics jobs](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-develop-user-defined-operators). Please review the article for details.   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.

```csharp
using Microsoft.Analytics.Interfaces;
using Microsoft.Analytics.Types.Sql;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;

namespace ReferenceGuide_Examples
{
    public class CountryName : IProcessor
    {
        private static IDictionary<string, string> CountryTranslation = new Dictionary<string, string>
        {
            {
                "Deutschland", "Germany"
            },
            {
                "Schwiiz", "Switzerland"
            },
            {
                "UK", "United Kingdom"
            },
            {
                "USA", "United States of America"
            },
            {
                "中国", "PR China"
            }
        };

        public override IRow Process(IRow input, IUpdatableRow output)
        {
            string Country = input.Get<string>("Country");

            if (CountryTranslation.Keys.Contains(Country))
            {
                Country = CountryTranslation[Country];
            }

            output.Set<string>("Country", Country);
            return output.AsReadOnly();
        }
    }
}
```

**Using User-Defined Processor - CountryName**  
Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```sql
@drivers = 
    SELECT * FROM 
        ( VALUES
        ("1", "Maria Anders", "Obere Str. 57", "Berlin", "12209", "Germany"),
        ("3", "Antonio Moreno", "Mataderos  2312", "México D.F.", "5023", "Mexico"),
        ("4", "Thomas Hardy", "120 Hanover Sq.", "London", "WA1 1DP", "UK"),
        ("5", "Christina Berglund", "Berguvsvägen  8", "Luleå", "S-958 22", "Sweden"),
        ("8", "Martín Sommer", "C/ Araquil, 67", "Madrid", "28023", "Spain"),
        ("9", "Laurence Lebihan", "12, rue des Bouchers", "Marseille", "13008", "France"),
        ("10", "Elizabeth Lincoln", "23 Tsawassen Blvd.", "Tsawassen", "T2F 8M4", "Canada"),
        ("14", "Yang Wang", "Hauptstr. 29", "Bern", "3012", "Switzerland"),
        ("32", "Howard Snyder", "2732 Baker Blvd.", "Eugene", "97403", "USA"),
        ("92", "邓小平", "", "牌坊村", "", "中国")
        ) AS T(UserID, Name, Address, City, PostalCode, Country);

 @drivers_CountryName =
     PROCESS @drivers
     PRODUCE UserID,
             Name,
             Address,
             City,
             PostalCode,
             Country
     READONLY UserID, Name, Address, City, PostalCode
     REQUIRED Country
     USING new ReferenceGuide_Examples.CountryName();    

OUTPUT @drivers_CountryName
TO "/ReferenceGuide/QSE/PrimaryRowsetExpressions/Process/CountryName.txt"
USING Outputters.Text(Encoding.Unicode);
```

**Processor with ORDER BY and FETCH**   
The [ORDER BY clause with FETCH](order-by-and-offset-fetch-clause-u-sql.md) allows the selection of a limited number of rows based on the specified order.
This examples continues to use `CountryName` defined earlier.
```sql
// Same as previous example but only returns top 3 records ordered by Country
 @drivers_CountryName =
     PROCESS @drivers
     PRODUCE UserID,
             Name,
             Address,
             City,
             PostalCode,
             Country
     READONLY UserID, Name, Address, City, PostalCode
     REQUIRED Country
     USING new ReferenceGuide_Examples.CountryName()
     ORDER BY Country ASC FETCH 3 ROWS;    

OUTPUT @drivers_CountryName
TO "/ReferenceGuide/QSE/PrimaryRowsetExpressions/Process/CountryName_fetch3.txt"
USING Outputters.Text(Encoding.Unicode);
```
  
### See Also 
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md) 
* [Output Statement (U-SQL)](output-statement-u-sql.md)  
* [U-SQL Programmability Guide: User-Defined Processor](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-processor)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)  
* [How to register U-SQL Assemblies in your U-SQL Catalog](https://blogs.msdn.microsoft.com/azuredatalake/2016/08/26/how-to-register-u-sql-assemblies-in-your-u-sql-catalog/)

