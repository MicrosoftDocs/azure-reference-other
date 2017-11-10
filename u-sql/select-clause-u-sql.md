---
title: "SELECT Clause (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-04-27"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 913be2b2-26ff-4932-9468-665a22e59afc
caps.latest.revision: 17
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# SELECT Clause (U-SQL)
The SELECT clause defines the projection of the SELECT expression, i.e., it specifies the resulting structure and values of the rowset it produces. The result has at least one column.  
  
<table><th>Syntax</th><tr><td><pre>
Select_Clause :=                                                                                         
    'SELECT' ['<a href="#dist">DISTINCT</a>'] Select_Item_List.<br />
Select_Item_List :=  
    <a href="#s_item">Select_Item</a> { ',' <a href="#s_item">Select_Item</a> }.
</pre></td></tr></table>

### Semantics of Syntax Elements    
- <a name="s_item"></a>**`Select_Item`**  
Each column is either specified by a reference to a column identifier in the SELECT’s rowset that the other clauses of the SELECT expression produces, or by an expression:

   <table><th>Syntax</th><tr><td><pre>
Select_Item:                                                                                        
    Column_Identifier [<a href="#col_alias">Column_Alias</a>]  
|   expression <a href="#col_alias">Column_Alias</a>.<br />
Column_Identifier :=  
    [(Rowset_Variable | <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>) '.']  
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.<br /><br />     
<a href="#col_alias">Column_Alias</a> :=  
    'AS' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.  
</pre></td></tr></table>
  
    The select clause can refer to column identifiers either by providing the [quoted or unquoted identifier](../USQL/u-sql-identifiers.md) of the column, or by prepending the rowset/table alias or rowset variable name to identify the rowset to which the column belongs.  
    
-   <a name="col_alias"></a>**`Column_Alias`**      
    The column alias is not  required for SELECT clause expressions that end with a property or field access where the inferred name does not conflict with any other column name. The column name will be derived from the name of the property/field.
  
    The identifier can be renamed by specifying a different column alias. The expression can – but does not need to – refer to columns in the SELECT’s rowset. The expression can be any U-SQL expression that produces an instance of one of the built-in U-SQL types and will have to be named with a column alias, otherwise an error will be raised.  
  
    Please note that `AS` is case-sensitive and that C# also provides the type cast operator `as`. The following SELECT clause would be interpreted as an attempt to cast the column `c` to a non-existing type `newcol` and fail:  
 
    ```
    SELECT c as newcol FROM …
    ```

-   <a name="dist"></a>**`DISTINCT`**  
If the optional `DISTINCT` keyword is specified, then the SELECT expression will eliminate duplicate rows. It requires that every selected column is of a comparable type, otherwise an error is raised.  
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Using a column alias**  
```
@t =
  SELECT *
  FROM (VALUES("1965")) AS T(c1);

@r =
    SELECT c1.ToString().Length,                // alias is not required; "Length" alias derived
           2 + c1.ToString().Length AS Length2  // alias is required; top-level operator is "+", not ".Length"
    FROM @t;

OUTPUT @r
TO "/ReferenceGuide/DML/QSE/noAlias.txt"
USING Outputters.Tsv(outputHeader : true);
```

**Using DISTINCT**   
The following query selects the distinct regions from the `@searchlog` rowset.  
```
@rs1 =     
    SELECT DISTINCT Region  
    FROM @searchlog;
```
It returns the following result in non-determinstic order:  
  
Region |  
--------- |  
en-ca |   
en-ch |   
en-fr |   
en-gb |   
en-gr |   
en-mx |   
en_us |   
  
### See Also 
* [Query Statements and Expressions (U-SQL)](../USQL/query-statements-and-expressions-u-sql.md)
* [Data Modification Language (DML) Statements (U-SQL)](../USQL/data-modification-language-dml-statements-u-sql.md)    
* [Output Statement (U-SQL)](../USQL/output-statement-u-sql.md)  



