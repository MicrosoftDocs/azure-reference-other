---
title: "CREATE FUNCTION (U-SQL): Table-valued Function | Microsoft Docs"
ms.custom: ""
ms.date: "2017-06-29"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 95421ea1-0455-4b97-996c-3068e2dc57b7
caps.latest.revision: 27
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CREATE FUNCTION (U-SQL): Table-valued Function
The CREATE FUNCTION statement allows to create a table-valued function (often referred to as TVF).  

<table><th align="left">Syntax</th><tr><td><pre>
Create_TV_Function_Statement :=                                                                          
    'CREATE' 'FUNCTION' [<a href="#INE">'IF' 'NOT' 'EXISTS'</a>] <a href="#Ident">Identifier</a> <a href="#tvf_sig">TVF_Signature</a>  
    ['AS'] 'BEGIN'  
    <a href="#tvf_s_lst">TVF_Statement_List</a>   
    'END'.
</pre></td></tr></table>

### Semantics of Syntax Elements    
This statement creates the function with the specified identifier and function signature based on the provided statement list.  
  
-   <a name="Ident"></a>**`Identifier`**  
    Specifies the name of the table-valued function. If the `Identifier` is a three-part identifier, the function will be created in the specified database and schema. If it is a two-part identifier, then the function will be created in the specified schema of the current database context. If the identifier is a simple identifier, then the function will be created in the current database and schema context.  
  
    If an object of the given name already exists in the specified database and schema context or the user has no permissions to create a function, an error is raised.  
  
-   <a name="INE"></a>**`IF NOT EXISTS`**    
    If the optional `IF NOT EXISTS` is specified, then the statement creates the function if it does not already exist, or succeeds without changes if the function already exists and the user has permission to at least enumerate all existing functions.  
  
- <a name="tvf_sig"></a>**`TVF_Signature`**     
  The function signature provides the arguments and their types and optional default values and the return type of the function:  
  
  <table><th>Syntax</th><tr><td><pre>
  TVF_Signature :=                                                                                    
      '(' [Parameter_List] ')' TVF_Returns.<br />
  Parameter_List :=  
      Parameter {',' Parameter}.
  </pre></td></table>
  
  - **`Parameter`**  
    A parameter defines the name of the parameter in form of a variable local to the function body. Its type is either a [built-in U-SQL type](../USQL/built-in-u-sql-types.md), which optionally can be initialized with a default value, or a named or anonymous table type:
    
    <table><th>Syntax</th><tr><td><pre>
    Parameter :=                                                                                   
        User_Variable ( Type_Name [Default_Parameter_Value]
                      | Table_Type
                      | Anonymous_Table_Type).<br />
    Default_Parameter_Value :=
        '=' function_argument_expression.<br />
    Table_Type :=
        Identifier.<br />
    Anonymous_Table_Type :=
        'TABLE' '(' Column_Definition_List ')'.</pre></td></table>
        
  - **`TVF_Returns`**  
    The return of a TVF is specified by either a single return rowset or a list of return rowsets. Each returned rowset is specified by a rowset variable name and its return type that is either specified as a reference to a registered [U-SQL table type](../USQL/u-sql-table-types.md) or an anonymous table type.

    <table><th>Syntax</th><tr><td><pre>
    TVF_Returns :=
        'RETURNS' (Return_Rowset | '(' Return_Rowset_List ')').<br />
    Return_Rowset :=
        Rowset_Variable Return_Table_Type.<br />
    Return_Table_Type :=
        Anonymous_Table_Type | Table_Type.<br />
    Return_Rowset_List :=
        Return_Rowset {',' Return_Rowset}.</pre></td></table>
    
  > [!TIP]
  > In a future refresh, table-valued functions will disallow a result variable from having the same name as any of the function's parameters.

- <a name="tvf_s_lst"></a>**`TVF_Statement_List`**  
  The resulting values of a TVF are being calculated inside the table-valued function’s body. The function body consists of a sequence of U-SQL query statements. The last statement for a given return rowset variable will be returned as the resulting rowset. If the statement’s inferred type is not the same as the specified return type, a compilation error will be reported.  

  <table><th>Syntax</th><tr><td><pre>
  TVF_Statement_List :=                                                                               
      { [TVF_Statement] ';' }.<br />  
  TVF_Statement :=  
      TVF_Statement_Body  
      [Optimizer_Hint_Clause].<br />   
  TVF_Statement_Body :=  
      <a href="use-database-u-sql.md">Use_Statement</a>  
  |   <a href="variables-u-sql.md">Declare_Variable_Statement</a>  
  |   <a href="import-package-u-sql.md">Import_Package_Statement</a> 
  |   <a href="reference-assembly-u-sql.md">Reference_Assembly_Statement</a>  
  |   Deploy_Resource_Statement  
  |   <a href="query-statements-and-expressions-u-sql.md">Query_Statement</a>.</pre></td></table> 

  Please follow the links for more on the general nature of the statements. Note that in order to avoid side-effects that cannot inlined into a query expression, you cannot call [INSERT](../USQL/insert-u-sql.md) or [OUTPUT](../USQL/output-statement-u-sql.md) statements or call procedures that may have side-effects.  
  
  Setting the context with a USE statement, declaring variables or referencing assembly statements inside a function body will only affect the static context of the table-valued function’s body and will not be visible in the calling context or the static context of the definition of an object called within (e.g., another TVF).  
 
  The function body’s own static context is not affected by the calling environment’s static context. E.g., a [USE DATABASE](../USQL/use-database-u-sql.md)  statement in the script that is calling the function is not affecting the function’s default static database context and variables defined outside a function body will not be visible.  
  
  Assemblies referenced in the function body will however be visible in the calling environment’s dynamic context and will be visible in any of the called contexts and the function’s own dynamic context. In addition, the function will inherit the loaded assemblies from the calling environment.  
  
  Deploying a resource inside a function will become visible to the whole script at runtime, similar to referencing an assembly and any resources deployed by the calling environment will be visible in the function’s dynamic context.  
  
  The compiler does not allow more than 50 nested function calls to prevent stack overflow. Please make sure that functions are called with less nesting.  See [Recursive TVF](#tvf_recursive) example, below.

> [!IMPORTANT]
> In the Public Preview, only a limited grammar check will be performed during creation of a table-valued function. Instead the grammar will be checked when the TVF gets compiled for usage. This behavior is subject to change in future releases.
  
### Examples    
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The examples below use the sample data provided with your Data Lake Analytics account. See [Prepare source data](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-get-started-portal#prepare-source-data) for additional information.

<a name="tvf_SearchLog">**Basic Syntax - tvf_SearchLog**</a>    
```
CREATE DATABASE IF NOT EXISTS TestReferenceDB; 
USE DATABASE TestReferenceDB; 

DROP FUNCTION IF EXISTS tvf_SearchLog;
CREATE FUNCTION tvf_SearchLog()
RETURNS @searchlog TABLE(UserId int, Start DateTime, Region string, Query string, Duration int?, Urls string, ClickedUrls string)
AS
BEGIN
    @searchlog =
        EXTRACT UserId int,
                Start DateTime,
                Region string,
                Query string,
                Duration int?,
                Urls string,
                ClickedUrls string
        FROM "/Samples/Data/SearchLog.tsv"
        USING Extractors.Tsv();
RETURN;
END;
```

**TVF with a parameter**   
The function declaration defines the function with one argument that allows to parameterize the contained query statements. The parameter `@Region` is of type string and initialized with the default `en-gb`. The function declaration also declares the resulting table type which will be checked against the resulting query expression’s type. The query body is an extraction statement followed by a selection that applies the filter.
```
DROP FUNCTION IF EXISTS TestReferenceDB.dbo.SearchLogPerRegion;
CREATE FUNCTION TestReferenceDB.dbo.SearchLogPerRegion(@Region string = "en-gb")
RETURNS @res TABLE(UserId int, Start DateTime, Region string, Query string, Duration int, Urls string, ClickedUrls string)
AS
BEGIN
    @sl =
        EXTRACT UserId int,
                Start DateTime,
                Region string,
                Query string,
                Duration int,
                Urls string,
                ClickedUrls string
        FROM "/Samples/Data/SearchLog.tsv"
        USING Extractors.Tsv();

    @res =
        SELECT *
        FROM @sl
        WHERE Region == @Region;  
END;   
```

**TVF that returns multiple-rowsets**  
Similar to above function except this TVF will 1) return a rowset that contains all values for the defined region, and then 2) return a second rowset that contains value for the remaining regions.
```
DROP FUNCTION IF EXISTS TestReferenceDB.dbo.SearchLogPerRegionWithRemainder;
CREATE FUNCTION TestReferenceDB.dbo.SearchLogPerRegionWithRemainder(@Region string = "en-gb")
RETURNS (@definedRegion, @remainderRegions)

/* alternative header
RETURNS (
@definedRegion TABLE (UserId int, Start DateTime, Region string, Query string, Duration int, Urls string, ClickedUrls string),
@remainderRegions TABLE (UserId int, Start DateTime, Region string, Query string, Duration int, Urls string, ClickedUrls string)
)
*/

AS
BEGIN
    @searchlog  =
        EXTRACT UserId int,
                Start DateTime,
                Region string,
                Query string,
                Duration int,
                Urls string,
                ClickedUrls string
        FROM "/Samples/Data/SearchLog.tsv"
        USING Extractors.Tsv();

    @definedRegion =
        SELECT *
        FROM @searchlog 
        WHERE Region == @Region;  

    @remainderRegions =
        SELECT *
        FROM @searchlog 
        WHERE Region != @Region;  
END;  
```

<a name="tvf_recursive">**Recursive TVF**</a>  
The TVF below calls itself and increments a value by one.  The recursive calls continue based on the value passed to the parameter `@MaxIterations`.  A value greater than 50 to `@MaxIterations` will cause the function to error.  Consider the options to avoid such an error.  Here, you could add code to the call to prevent a value greater than 50 to be passed to `@MaxIterations`.  The function definition could also be modified to alter the behavior when `@CurrentIteration` exceeds 50 and/or when `@MaxIterations` is passed a value greater than 50.
```
USE TestReferenceDB;

// Function definition
USE TestReferenceDB;

DROP FUNCTION IF EXISTS dbo.SimpleRecursion;
CREATE FUNCTION dbo.SimpleRecursion(
        @baseValues TABLE(id1 int, id2 int), 
        @CurrentIteration int = 0, @MaxIterations int = 5)
RETURNS @result TABLE(id1 int, id2 int)
AS
BEGIN
    IF (@CurrentIteration >= @MaxIterations) THEN
        @result = SELECT * FROM @baseValues;
    ELSE
        @baseValues = SELECT * FROM @baseValues UNION SELECT @CurrentIteration + 1 AS id1, @MaxIterations AS id2 FROM @baseValues;
        @result = dbo.SimpleRecursion(@baseValues, @CurrentIteration + 1, @MaxIterations);   
    END; 
END; 

// Function call
@baseValues =
    SELECT * FROM (
        VALUES
            (0, 0) 
            ) AS T(id1, id2);

OUTPUT dbo.SimpleRecursion(@baseValues, 0, 5)
TO "/Output/ReferenceGuide/DDL/Functions/callSimpleRecursion.txt"
USING Outputters.Tsv();  
```

**Additional Examples**   
* [Table type in a table-valued function as a returned value](../USQL/create-type-u-sql.md#function_return)  
* [Table-Valued Function Expression (U-SQL)](../USQL/table-valued-function-expression-u-sql.md) for examples on how to call the above functions.
  
  
### See Also    
* [U-SQL Functions](../USQL/u-sql-functions.md)  
* [U-SQL Table-valued Functions](../USQL/u-sql-table-valued-functions.md)  
* [DROP FUNCTION (U-SQL)](../USQL/drop-function-u-sql.md)  
* [Table-Valued Function Expression (U-SQL)](../USQL/table-valued-function-expression-u-sql.md)  
* [Built-in Functions (U-SQL)](../USQL/built-in-functions-u-sql.md) 
* [Data Definition Language (DDL) Statements (U-SQL)](../USQL/data-definition-language-ddl-statements-u-sql.md)   
