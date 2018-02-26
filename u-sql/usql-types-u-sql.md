---
title: "usql.types (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "10/05/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6d3488b9-5380-4b48-bd4b-97b59afca76d
caps.latest.revision: 3
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# usql.types (U-SQL)

Contains a row for each built-in type as well as user-defined types (both scalar and table types) belonging to the schemas in the current database context. Since user-defined types are not directly registered in the U-SQL catalog (but are part of the assemblies), they are not included in this view.

> [!IMPORTANT]
> This catalog view's content is subject to change in a future refresh!

Column name  |Data type  |Description  
---------|---------|---------
type_id_guid     |Guid         |Types's unique identifier         
name     |string         |Type's name alias (unique within the type family)         
type_family     |string         |Name of the type system family, together with the type name's alias, uniquely identifies the type. U-SQL supports the following values:<br><br> SQL = SQL Server Type system family<br><br> C# = C# type system family<br><br> U-SQL = U-SQL table types         
qualified_name     |string         |Fully qualified name of the underlying C# type library representing the type. This name uniquely identifies the type.         
schema_id_guid     |Guid         |ID of the database schema the type belongs to
is_explicit_nullable|bool?|True = Type can be marked explicitly as nullable (e.g. int?)<br><br> False = Type cannot be marked explicitly as nullable (e.g. C#'s string)<br><br> Null = Is a table type
is_user_defined|bool|True = User-defined type<br><br> False = Built-in data type
is_assembly_type |bool|True = Implementation of the type is defined in a CLR assembly<br><br> False = Type is based on a SQL Server system data type or is a U-SQL table type
is_table_type|bool|Indicates if the type is a table type
is_complex|bool|True = Type is considered complex for serialization and query purposes<br><br> False = Type is considered scalar for serialization and query purposes  
precision|int?|Indicates the max precision of the type if it is a numeric type, 0 otherwise, null if it is not a built-in type
scale|int?|Indicates the max scale of the type if it is a numeric type, 0 otherwise, null if it is not a built-in type
is_nullable|bool?|False = Type implicitly allows null value<br><br> True = Type does not implicitly allow null value<br><br> Null = Is a table type
is_precise|int?|Supported values are:<br><br> 0 = Type semantics is imprecise<br><br> 1 = Type semantics is precise<br><br> 2 = Type semantics regarding precision is determined based on other aspects (e.g., in complex types, if all referenced types are precise then the complex type is precise)<br><br> Null = Is a table type
is_foldable|bool?|False =   Expressions of this type cannot be constant-folded in query processing<br><br> True = Expressions of this type can be constant-folded<br><br> Null = Is a table type
is_comparable|bool?|False = Values of this type cannot be compared or ordered<br><br> True = Values of this type can be compared and ordered<br><br> Null = Is a table type
is_real_number|bool?|False = Value of this type is not a real number<br><br> True = Value of this type is a real number<br><br> Null = Not a built-in type


### Examples
The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504). 


 **Query the usql.types view**
 ```sql
USE TestReferenceDB;

OUTPUT usql.types
TO "/ReferenceGuide/CatalogViews/types.txt"
USING Outputters.Tsv(outputHeader:true);
```


### See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)



