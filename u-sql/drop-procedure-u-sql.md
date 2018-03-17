---
title: "DROP PROCEDURE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 884fa21f-4a2a-4b77-a204-bd7711dbec52
caps.latest.revision: 5
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# DROP PROCEDURE (U-SQL)
The `DROP PROCEDURE` statement drops the specified procedure.  
  
> [!WARNING]
> **This operation cannot be undone!**
  
<table><th align="left">Syntax</th><tr><td><pre>
Drop_Proc_Statement :=                                                                                   
    'DROP' 'PROCEDURE' [<a href="#IE">'IF' 'EXISTS'</a>] <a href="#Ident">Identifier</a>.
</pre></td></tr></table>
 
### Semantics of Syntax Elements    
-   <a name="Ident"></a>**`Identifier`**   
    Specifies the name of the procedure to be dropped. If the procedure name is a fully-specified three-part name, the procedure in the specified database and schema will be dropped. If the name is a two-part name, the procedure will be dropped in the current database context and specified schema. If the name is a simple identifier, then the procedure will be dropped in the current database and schema context.  
  
-   <a name="IE"></a>**`IF EXISTS`**   
    If a procedure of the given name does not exist, or the user has no permissions to drop the procedure, an error is raised. If the optional `IF EXISTS` is specified, then the statement drops the procedure if it already exists, or succeeds without changes if the procedure does not exist or the user has no permission to at least enumerate all existing procedures.  
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://channel9.msdn.com/Series/AzureDataLake/USQL-LocalRun).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples utilize the procedures created from [CREATE PROCEDURE (U-SQL)](create-procedure-u-sql.md).

```sql
// Will error if not exists
DROP PROCEDURE TestReferenceDB.dbo.myStoredProcWithParameters;

DROP PROCEDURE IF EXISTS TestReferenceDB.dbo.myFirstStoredProc;
```

  
### See Also    
* [U-SQL Procedures](u-sql-procedures.md)  
* [CREATE PROCEDURE (U-SQL)](create-procedure-u-sql.md)  
* [Calling a Procedure (U-SQL)](calling-a-procedure-u-sql.md)   
