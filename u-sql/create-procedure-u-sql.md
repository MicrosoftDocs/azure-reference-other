---
title: "CREATE PROCEDURE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-08-22"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: d76e025a-b482-48bf-b157-eb7148bf6401
caps.latest.revision: 16
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CREATE PROCEDURE (U-SQL)
U-SQL creates a procedure with the `CREATE PROCEDURE` statement.  For information on calling a procedure, see [Calling a Procedure (U-SQL)](../u-sql/calling-a-procedure-u-sql.md)

<table><th align="left">Syntax</th><tr><td><pre>
Create_Proc_Statement :=                                                                                 
    'CREATE' 'PROCEDURE' [<a href="#INE">'IF' 'NOT' 'EXISTS'</a>] <a href="#Ident">Identifier</a>   
    '(' [<a href="#param_lst">Parameter_List</a>] ')'  
    ['AS']  
    'BEGIN'  
    <a href="#proc_lst">Proc_Statement_List</a>  
    'END'.
</pre></td></tr></table>

### Semantics of Syntax Elements    
This statement creates the procedure with the specified identifier and parameters based on the provided statement list.  
  
-   <a name="Ident"></a>**`Identifier`**   
    Specifies the name of the procedure. If the `Identifier` is a three-part identifier, the procedure will be created in the specified database and schema. If it is a two-part identifier, then the procedure will be created in the specified schema of the current database context. If the identifier is a simple identifier, then the procedure will be created in the current database and schema context.  
  
    If an object of the given name already exists in the specified database and schema context or the user has no permissions to create a procedure, an error is raised.  
  
-   <a name="INE"></a>**`IF NOT EXISTS`**  
    If the optional `IF NOT EXISTS` is specified, then the statement creates the procedure if it does not already exist, or succeeds without changes if the procedure already exists and the user has permission to at least enumerate all existing procedures.  
  
- <a name="param_lst"></a>**`Parameter_List`**    
  The parameter list provides the arguments and their types and optional default values. The [U-SQL function section](../u-sql/u-sql-functions.md) provides more details about the syntax and semantics of the parameter list.  
  
- <a name="proc_lst"></a>**`Proc_Statement_List`**     
  The statements inside a stored procedure can be any statements except for `CREATE FUNCTION`, `CREATE PROCEDURE`, `DROP FUNCTION`, `DROP PROCEDURE`.  
 
  <table><th>Syntax</th><tr><td><pre>
  Proc_Statement_List :=                                                                              
      { [Proc_Statement] ';' }.<br /> 
  Proc_Statement :=  
      Proc_Statement_Body  
      [Optimizer_Hint_Clause].<br />   
  Proc_Statement_Body :=   
      <a href="u-sql-metadata-object-naming-and-name-contexts.md">Use_Statement</a>  
  |   <a href="variables-u-sql.md">Declare_Variable_Statement</a>  
  |   <a href="import-package-u-sql.md">Import_Package_Statement</a> 
  |   <a href="reference-assembly-u-sql.md">Reference_Assembly_Statement</a>   
  |   Deploy_Resource_Statement  
  |   <a href="query-statements-and-expressions-u-sql.md">Query_Statement</a>  
  |   <a href="calling-a-procedure-u-sql.md">Procedure_Call</a> 
  |   <a href="#pbs">ProcBody_DDL_Statement</a> 
  |   <a href="data-modification-language-dml-statements-u-sql.md">DML_Statement</a> 
  |   <a href="output-statement-u-sql.md">Output_Statement</a>.<br /><br />    
  <a name="pbs"></a>ProcBody_DDL_Statement :=   
      <a href="u-sql-databases.md">DB_DDL_Statement</a>  
  |   <a href="u-sql-database-schemas.md">Schema_DDL_Statement</a>  
  |   <a href="u-sql-tables.md">Table_DDL_Statement</a>  
  |   <a href="u-sql-indexes.md">Index_DDL_Statement</a>  
  |   <a href="u-sql-statistics.md">Statistics_DDL_Statement</a>  
  |   <a href="u-sql-views.md">View_DDL_Statement</a>  
  |   <a href="u-sql-packages.md">Package_DDL_Statement</a>  
  |   <a href="u-sql-assemblies.md">Assembly_DDL_Statement</a>  
  |   <a href="u-sql-data-sources.md">Datasource_DDL_Statement</a>  
  |   <a href="user-defined-u-sql-types.md">Type_DDL_Statement</a>.
  </pre></td></table>

  Please follow the links for more on the general nature of the statements.  
  
Note that setting the context inside the procedure body with a USE statement, declaring variables or referencing assembly statements are only affecting the static context of the procedure’s body and will not be visible in the calling context or the static context of the definition of an object called within (e.g., the script or another procedure).  
  
The procedure’s own static context is not affected by the calling environment’s static context. E.g., a [USE DATABASE](../u-sql/use-database-u-sql.md)  statement or a variable declaration in the script that is calling the procedure is not affecting the procedure’s default static database context and is not visible inside the procedure body**.**  
  
Assemblies referenced in a procedure body will however be visible in the calling environment’s dynamic context at runtime and will be visible in any of the called contexts and the procedure’s own dynamic context. In addition, the procedure’s dynamic context will inherit the loaded assemblies from the calling environment.  
  
Deploying a resource inside a procedure will become visible to the whole script at runtime, similar to referencing an assembly and any resources deployed by the calling environment will be visible in the procedure’s dynamic context.  
 
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below utilize the table dbo.somePeople as defined below.
  
**Dataset**   
```
// Create database
CREATE DATABASE IF NOT EXISTS TestReferenceDB; 
USE DATABASE TestReferenceDB; 

// Create table
DROP TABLE IF EXISTS dbo.somePeople;
CREATE TABLE dbo.somePeople
(
    EmpID int,
    EmpName string,
    DeptID int,
    Salary int?,
    StartDate DateTime,
    PhoneNumbers string,
    INDEX clx_EmpID CLUSTERED(EmpID ASC)
    DISTRIBUTED BY HASH (EmpID) 
);

// Populate table
INSERT INTO dbo.somePeople
VALUES
(1, "Noah",   100, (int?)10000, new DateTime(2012,05,31), "cell:030-0074321,office:030-0076545"),
(2, "Sophia", 100, (int?)15000, new DateTime(2012,03,19), "cell:(5) 555-4729,office:(5) 555-3745"),
(3, "Liam",   100, (int?)30000, new DateTime(2014,09,14), ""),
(6, "Emma",   200, (int?)8000,  new DateTime(2014,03,08), (string)null),
(7, "Jacob",  200, (int?)8000,  new DateTime(2014,09,02), "cell:(5) 555-3932"),
(8, "Olivia", 200, (int?)8000,  new DateTime(2013,12,11), "cell:88.60.15.31,office:88.60.15.32"),
(9, "Mason",  300, (int?)50000, new DateTime(2016,01,01), "cell:(91) 555 22 82,office:(91) 555 91 99, home:(425) 555-2819"),
(10, "Ava",   400, (int?)15000, new DateTime(2014,09,14), "cell:91.24.45.40,office:91.24.45.41"),
(11, "Ethan", 400, (int?)9000,  new DateTime(2015,08,22), "cell:(604) 555-4729,office:(604) 555-3745");

/* optional
OUTPUT TestReferenceDB.dbo.somePeople
TO "/Output/ReferenceGuide/DDL/Types/somePeople.txt"
ORDER BY EmpID ASC
USING Outputters.Tsv();
*/
```

**myFirstStoredProc**    
The following example creates a stored procedure called `myFirstStoredProc` that outputs the content of `somePeople` to a CSV file.
```
DROP PROCEDURE IF EXISTS TestReferenceDB.dbo.myFirstStoredProc;
CREATE PROCEDURE TestReferenceDB.dbo.myFirstStoredProc()  
AS  
BEGIN 
    @result =  
        SELECT *  
        FROM TestReferenceDB.dbo.somePeople;  
  
    OUTPUT @result  
    TO "/Output/ReferenceGuide/DDL/Procedure/myFirstStoredProc.csv"  
    USING Outputters.Csv();    
END;
```

**myStoredProcWithParameters**   
The following example creates a stored procedure called `myStoredProcWithParameters` that outputs the content of `somePeople` that matches the `city` and `date` passed to the procedure.
```
DROP PROCEDURE IF EXISTS TestReferenceDB.dbo.myStoredProcWithParameters;
CREATE PROCEDURE TestReferenceDB.dbo.myStoredProcWithParameters(@deptID int, @startDate DateTime)  
AS  
BEGIN 
@result =  
    SELECT *  
    FROM TestReferenceDB.dbo.somePeople
    WHERE DeptID == @deptID  
    AND StartDate == @startDate;  
  
    OUTPUT @result  
    TO "/Output/ReferenceGuide/DDL/Procedure/myStoredProcWithParameters.csv"  
    USING Outputters.Csv();  
END;
```

**getPeople**   
The following example creates a stored procedure called `getPeople` that outputs the content of `somePeople` that matches the array of `DeptID` values passed to the procedure.
In addition, you can pass the location of the output to the `@filePath` parameter.  A default value for `@filePath` is assigned.
```
DROP PROCEDURE IF EXISTS TestReferenceDB.dbo.getPeople;
CREATE PROCEDURE TestReferenceDB.dbo.getPeople(
    @deptIDarray SQL.ARRAY<int>, 
    @filePath string = "/Output/ReferenceGuide/DDL/Procedure/getPeople.csv") 
AS  
BEGIN 
    @result =
        SELECT *
        FROM TestReferenceDB.dbo.somePeople
        WHERE @deptIDarray.Contains(DeptID);

    OUTPUT @result
    TO @filePath
    USING Outputters.Csv();
END;
```

**Additional Examples**   
* See [Procedure addPeople](../u-sql/create-type-u-sql.md#sproc_pass), a procedure that accepts a table type as a parameter.   
* See [Calling a Procedure (U-SQL)](../u-sql/calling-a-procedure-u-sql.md) for examples on how to call the above procedures.  
  
### See Also
* [U-SQL Procedures](../u-sql/u-sql-procedures.md)  
* [DROP PROCEDURE (U-SQL)](../u-sql/drop-procedure-u-sql.md)  
* [Calling a Procedure (U-SQL)](../u-sql/calling-a-procedure-u-sql.md)
* [U-SQL Packages](../u-sql/u-sql-packages.md) 
