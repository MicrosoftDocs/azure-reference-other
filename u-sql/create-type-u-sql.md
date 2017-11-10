---
title: "CREATE TYPE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 287f9451-66a8-46f8-9aa9-11340b77a07b
caps.latest.revision: 12
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CREATE TYPE (U-SQL)
U-SQL can name and register table types with the `CREATE TYPE` statement.  

<table><th>Syntax</th><tr><td><pre>
Create_Type_Statement :=                                                                                 
    'CREATE' 'TYPE' [<a href="#INE">'IF' 'NOT' 'EXISTS'</a>] <a href="#t_ident">Type_Identifier</a>   
    'AS' Anonymous_Table_Type.<br /><br />
<a href="#t_ident">Type_Identifier</a> := 
    <a href="u-sql-identifiers.md">DB_Object_Identifier</a>.<br />
Anonymous_Table_Type :=  
    'TABLE' '(' <a href="#cdl">Column_Definition_List</a> ')'.  
</pre></td></tr></table>

### Semantics of Syntax Elements  
-   <a name="t_ident"></a>**`Type_Identifier`**   
Specifies the name of the type. If the identifier is a two-part identifier, then the type will be created in the specified database. If the identifier is a simple identifier, then the type will be created in the current database context.  
  
    If an object of the given name already exists in the specified database context or the user has no permissions to create a type, an error is raised.  
  
-   <a name="INE"></a>**`IF NOT EXISTS`**   
If the optional `IF NOT EXISTS` is specified, then the statement creates the type if it does not already exist, or succeeds without changes if the type already exists and the user has permission to at least enumerate all existing types.  
  
- <a name="cdl"></a>**`Column_Definition_List`**  
Defines the table schema as follows :
 
   <table><th>Syntax</th><tr><td><pre>
Column_Definition_List :=                                                                           
       Column_Definition { ',' Column_Definition }.  
</pre></td></tr></table>  
 
    - **`Column_Definition`**   
A column definition is of the form
    <table><th>Syntax</th><tr><td><pre>
Column_Definition :=    
<a></a>     <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> <a href="built-in-u-sql-types.md">Built_in_Type</a>.                                               <a></a>
    </pre></td></tr></table>
  
         Each column has an identifier that can be either a [quoted or unquoted identifier](../USQL/u-sql-identifiers.md) which is typed with one of the [built-in U-SQL types](../USQL/built-in-u-sql-types.md).   
  
  
### Examples    
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed locally.  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- Some of the examples below utilize the table `dbo.somePeople` as defined below.  

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

**Create Type**  
```
CREATE TYPE IF NOT EXISTS TestReferenceDB.dbo.PhoneType AS TABLE (
    EmpName string, 
    DeptID int,
    PhoneNumbers string
    );
``` 

<a name="function_return">**Table type in a table-valued function as a returned value**</a>   
This example utilizes the above table type in a table-valued function as a returned value.
```
USE DATABASE TestReferenceDB; 

// Create function utilizing the new type
DROP FUNCTION IF EXISTS dbo.getDeptPhoneNumbers;
CREATE FUNCTION dbo.getDeptPhoneNumbers(@DeptID int)
RETURNS @result PhoneType
// Using the table type allows you to use "RETURNS @result PhoneType" above
// as opposed to "RETURNS @result TABLE(EmpName string, DeptID int, PhoneNumbers string)"

AS
BEGIN
    @result =
        SELECT  EmpName, 
                DeptID,
                string.IsNullOrWhiteSpace(PhoneNumbers) ? "Unknown" : PhoneNumbers AS PhoneNumbers
        FROM TestReferenceDB.dbo.somePeople
        WHERE DeptID == @DeptID;  
END;  

// Pass a DeptID to the function and review results
OUTPUT TestReferenceDB.dbo.getDeptPhoneNumbers(100) 
TO "/Output/ReferenceGuide/DDL/Types/getDeptPhoneNumbers.txt"
USING Outputters.Tsv();
```

<a name="sproc_pass">**Table type in a stored procedure as a passed value**</a>   
This example utilizes the above table type in a stored procedure as a passed value.
```
USE DATABASE TestReferenceDB; 

// Create stored procedure utilizing the new type
DROP PROCEDURE IF EXISTS dbo.addPeople;
CREATE PROCEDURE dbo.addPeople (@MyTableParam PhoneType)
AS
BEGIN	
    @num = SELECT MAX(EmpID) AS maxEmpID FROM [TestReferenceDB].[dbo].[somePeople];

	INSERT INTO [TestReferenceDB].[dbo].[somePeople]
    (EmpID, StartDate, EmpName, DeptID, PhoneNumbers)
	SELECT  (int)maxEmpID + (int)ROW_NUMBER() OVER(ORDER BY DeptID) AS EmpID, 
            DateTime.Now AS StartDate,
            EmpName, DeptID, PhoneNumbers
	FROM @MyTableParam CROSS JOIN @num;
END;


// Populate a variable rowset to pass to the procedure
@morePeople = 
    SELECT * FROM 
        ( VALUES
        ("David",  800, "cell:(171) 555-1212"),
        ("Andrew", 100, "cell:(1) 135-5555,office:(1) 135-4892"),
        ("Jennie", 100, "cell:(5) 555-3392,office:(5) 555-7293")
        ) AS T(EmpName, DeptID, PhoneNumbers);

// Execute procedure and pass above values (table-valued parameter)
dbo.addPeople(@morePeople);  


/* execute separately from above-code
// verify
OUTPUT dbo.somePeople
TO "/Output/ReferenceGuide/DDL/Types/morePeople.txt"
ORDER BY EmpID ASC
USING Outputters.Tsv();
*/
```

  
### See Also
* [User-defined U-SQL Types](../USQL/user-defined-u-sql-types.md)  
* [DROP TYPE (U-SQL)](../USQL/drop-type-u-sql.md)  
* [Data Definition Language (DDL) Statements (U-SQL)](../USQL/data-definition-language-ddl-statements-u-sql.md)   
