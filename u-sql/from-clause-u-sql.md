---
title: "FROM Clause (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-04-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: d0e36e0d-8b2c-404b-84db-828c2cd2f17e
caps.latest.revision: 22
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# FROM Clause (U-SQL)
The FROM clause specifies the input rowsets to the SELECT expression and how the rowsets are being combined into the SELECT expression’s rowset.  
  
<table><th>Syntax</th><tr><td><pre>
Select_From_Clause :=                                                                                    
    'FROM' <a href="#row_src">Rowset_Source</a>.
</pre></td></tr></table>
  
### Semantics of Syntax Elements    
- <a name="row_src"></a>**`Rowset_Source`**   
There are many rowset sources from which can be selected:
   <table><th>Syntax</th><tr><td><pre>
Rowset_Source :=                                                                                    
       <a href="#als_row">Aliased_Rowset</a>
|      <a href="#tbl_vl_con">Table_Value_Constructor</a>
|      <a href="#join_exp">Join_Expression</a>
|      <a href="#apl_exp">Apply_Expression</a>
|      '(' <a href="#join_exp">Join_Expression</a> ')'.  
</pre></td></tr></table>  
   
    - <a name="als_row"></a>**`Aliased_Rowset`**    
Aliased rowsets are rowsets that may or may not need a table alias.
        <table><th>Syntax</th><tr><td><pre>
Aliased_Rowset :=
<a></a>         Rowset [Alias]
|        Rowset_Expression Alias.                                                              <a></a>
        </pre></td></tr></table>
  
      - **`Alias`**  
The rowset alias gives a name to the rowset that can be used in the remainder of the SELECT expression to refer to that specific rowset. It can be a [quoted or unquoted identifier](u-sql-identifiers.md):
        <table><th>Syntax</th><tr><td><pre>
Alias :=
<a></a>     'AS' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.                                                  <a></a> 
        </pre></td></tr></table>
          
      - **`Rowset`**  
The simplest rowset sources are a rowset variable such as `@rowset` that has been defined in a previous statement of the script and a table that has been created in the account’s catalog:
        <table><th>Syntax</th><tr><td><pre> 
Rowset :=
<a></a>     Rowset_Variable
|    Identifier.                                                                          <a></a>
        </pre></td></tr></table>
 
        A table can be referenced either with its fully 3-part qualified name, within the current database context with a 2-part name, or within the current database and schema context with a single-part name. Optionally, a table alias can be provided for an input rowset variable or table which then can be used in the remainder of the SELECT expression.  
        
        Providing a rowset alias is optional.  
  
      - **`Rowset_Expression`**  
U-SQL also provides the ability to query over nested [query expressions](query-statements-and-expressions-u-sql.md), [table-valued function calls](u-sql-select-selecting-from-a-function-call.md) or querying [external rowsets](u-sql-select-selecting-from-an-external-rowset.md). Follow the links for more details on each.
        
        In these cases, a rowset alias has to be provided and cannot be left out.
        <table><th>Syntax</th><tr><td><pre> 
Rowset_Expression :=
<a></a>       '(' <a href="query-statements-and-expressions-u-sql.md">Query_Expression</a> ')'
|      <a href="u-sql-select-selecting-from-a-function-call.md">Function_Call</a>
|      <a href="u-sql-select-selecting-from-an-external-rowset.md">External_Rowset_Expression</a>
|      <a href="pivot-and-unpivot-u-sql.md">Pivot_Expression</a>
|      <a href="pivot-and-unpivot-u-sql.md">Unpivot_Expression</a>.                                                        <a></a>
        </pre></td></tr></table>          

  - <a name="tbl_vl_con"></a>**`Table_Value_Constructor`**  
    U-SQL’s SELECT can also select from the [VALUES table value constructor](u-sql-select-selecting-from-the-values-table-value-constructor.md) that creates an inline table.  
  
  - <a name="join_exp"></a>**`Join_Expression`**  
    U-SQL’s SELECT can also select from many different types of [join expressions](u-sql-select-selecting-from-joins.md) that combine several rowsets.  

  - <a name="apl_exp"></a>**`Apply_Expression`**  
    U-SQL’s SELECT can also select from [CROSS and OUTER APPLY expressions](u-sql-select-selecting-from-cross-apply-and-outer-apply.md) that turn scalar values in the left-hand rowset’s rows into rowsets. Follow the above link for more details.

> [!NOTE]
> Unlike most SQL versions, U-SQL does not support the ability to join rowsets with the comma notation. Instead one needs to use the explicit ANSI SQL join syntax.
  
For example, this implicit join expression is not supported
```
SELECT * FROM T1, T2 WHERE T1.val == T2.val;
```
  
Instead the query expression has be written as
```
SELECT * FROM T1 INNER JOIN T2 ON T1.val == T2.val;
```
 
  
### See Also 
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md)  
* [Data Modification Language (DML) Statements (U-SQL)](data-modification-language-dml-statements-u-sql.md)    
* [Output Statement (U-SQL)](output-statement-u-sql.md)  

