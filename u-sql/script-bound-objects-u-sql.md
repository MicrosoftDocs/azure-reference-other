---
title: "Script Bound Objects (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2018-06-21"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# Script Bound Objects (U-SQL)
Script bound objects allow the creation of local temporary objects that are visible only in the current session.

The `DECLARE_Script_Bound_Object` statements will create the specified object type in the local context of the script. The objects are syntactically visible from their point of specification and will live for the duration of the script only. The provided name must be non-conflicting with any other script-bound object names or variable names or an error is raised.

The objects cannot be dropped nor altered, nor do they appear in the catalog views.

The script-bound objects are referred to in the same context as their catalog-bound equivalents using their variable names.

## Syntax
<pre>
DECLARE_Script_Bound_Object :=
    DECLARE_Script_Bound_Type
|   DECLARE_Script_Bound_Function
|   DECLARE_Script_Bound_Procedure
|   DECLARE_Script_Bound_View.

DECLARE_Script_Bound_Type := 
    'DECLARE' '<a href="create-type-u-sql.md">TYPE</a>' Local_DDL_Variable 'AS' Anonymous_Table_Type.

DECLARE_Script_Bound_Function :=
    'DECLARE' '<a href="create-function-u-sql-table-valued-function.md">FUNCTION</a>' Local_DDL_Variable <a href="create-function-u-sql-table-valued-function#tvf_sig">TVF_Signature</a>  
    ['AS'] 
    'BEGIN'  
        <a href="create-function-u-sql-table-valued-function#tvf_s_lst">TVF_Statement_List</a>   
    'END'.

DECLARE_Script_Bound_Procedure :=
    'DECLARE' '<a href="create-procedure-u-sql.md">PROCEDURE</a>' Local_DDL_Variable '(' [Parameter_List] ')'  
    ['AS']  
    'BEGIN'  
        <a href="create-procedure-u-sql#proc_lst">Proc_Statement_List</a>  
    'END'.

DECLARE_Script_Bound_View := 
    'DECLARE' '<a href="create-view-u-sql.md">VIEW</a>' Local_DDL_Variable 'AS' <a href="query-statements-and-expressions-u-sql.md">Query_Expression</a>.

Local_DDL_Variable := <a href="variables-u-sql.md">User_Variable</a>.
</pre>
<br />


## Semantics of Syntax Elements  
Please refer to the [documentation](data-definition-language-ddl-statements-u-sql.md) for the equivalent `CREATE` statements.


## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

 

**Basic Example**   
```sql
DECLARE FUNCTION @sl() RETURNS @searchlog AS
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
END;

OUTPUT @sl()
TO "/ReferenceGuide/DDL/ScriptBoundObjects/Example1.csv"
USING Outputters.Csv(outputHeader:true);
```


## See Also 
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md) 
* [CREATE FUNCTION (U-SQL): Table-valued Function](create-function-u-sql-table-valued-function/md)
