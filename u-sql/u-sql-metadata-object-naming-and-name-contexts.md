---
title: "USE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 25ac3e33-dec3-461c-8a13-ccda2d52bdeb
caps.latest.revision: 15
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---

# USE (U-SQL)   

## USE Statements (U-SQL)   
<table><th align="left">Syntax</th><tr><td><pre>
Use_Statement :=                                                                                         
     <a href="use-database-u-sql.md">Use_Database_Statement</a>
|    <a href="use-schema-u-sql.md">Use_Schema_Statement</a>.
</pre></td></tr></table>

## U-SQL Metadata Object Naming and Name Contexts
The U-SQL metadata system provides a default database and default schema context. In alignment with the traditional SQL Server defaults they are called `master` for the default database and `dbo` for each database’s default schema. Please note that the metadata names are always case-sensitive.  
  
U-SQL uses the concepts of a *static database context* and *static schema context* which designate the default database and schema names that are used to resolve names that are not fully qualified during both compilation and execution:  
  
All unqualified, single-part metadata object names (such as functions and table names) will be resolved against the current static schema context within the current static database context. Individual names can overwrite the resolution by using multi-part names (so called qualified names). One can use either two-parts identifiers of the form `schema.object` to refer to a schema object in a different schema than the context schema, or use a three-part identifier of the form `database.schema.object` to refer to an object in a different database than the current context database. E.g., `T` will be resolved against the current static context, `S.T` will resolve the object name `T` in the schema `S` in the current static database context, and `D.S.T` will resolve the object name `T` in the schema `S` in the database `D`. See the section on [U-SQL Identifiers](u-sql-identifiers.md) for more information.   
  
Note that names inside U-SQL functions are resolved based on the context during compilation of the function, and not the dynamic context during use.  
  
The default static database and static schema contexts within a script can be changed with a USE statement.  
  
### See Also
* [Identifiers (U-SQL)](identifiers-u-sql.md) 
* [Securing Meta Data Objects](securing-meta-data-objects.md) 
