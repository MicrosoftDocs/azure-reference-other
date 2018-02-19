---
title: "DROP TYPE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 5fe7d149-2f9b-40ac-9245-74b98a99ff04
caps.latest.revision: 8
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# DROP TYPE (U-SQL)
U-SQL named types can be deleted with the `DROP TYPE` statement.  

> [!WARNING]
> **This operation cannot be undone!**

<table><th align="left">Syntax</th><tr><td><pre>
Drop_Type_Statement :=                                                                                   
    'DROP' 'TYPE' [<a href="#IE">'IF' 'EXISTS'</a>] <a href="#t_ident">Type_Identifier</a>.<br />
<a href="#t_ident">Type_Identifier</a> := 
    <a href="u-sql-identifiers.md">DB_Object_Identifier</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements    
-   <a name="t_ident"></a>**`Type_Identifier`**   
Specifies the type to be dropped in the current static database context. If the name is a two-part name, the type will be dropped in the specified database. If the name is a simple identifier, then the procedure will be dropped in the current database context.  
  
    If a type of the given name does not exist, or the user has no permissions to drop the type, an error is raised.  
  
-   <a name="IE"></a>**`IF EXISTS`**   
If the optional `IF EXISTS` is specified, then the statement drops the type if it exists, or succeeds without changes if the type does not exist or the user has no permission to at least enumerate all existing types.  
  
### Example    
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script can be executed locally.  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
```sql
DROP TYPE TestReferenceDB.dbo.PhoneType;
```
  
### See Also
* [User-defined U-SQL Types](user-defined-u-sql-types.md)  
* [CREATE TYPE (U-SQL)](create-type-u-sql.md)  
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)   

