---
title: "Query Statements and Expressions (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-16"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 47fe30cc-dd08-4ab5-bac8-37de08588b4a
caps.latest.revision: 32
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Query Statements and Expressions (U-SQL)
The core processing capability of U-SQL is to transform between rowsets using query expressions. This is done by combining query statements in a [U-SQL script](../USQL/u-sql-scripts.md).  
  
Since the current version of the Azure Data Lake Analytics service is only executing batch scripts, a query expression cannot be returned directly. It always has to be either output into a table with an [INSERT](../USQL/insert-u-sql.md) statement or a file using an [`OUTPUT`](../USQL/output-statement-u-sql.md) statement, or assigned to a rowset variable.  
  
<table><th align="left">Syntax U-SQL Query Statements</th><tr><td><pre>
Query_Statement :=                                                                                       
     <a href="#row_var">Rowset_Variable</a> '=' <a href="#qry_exp_fetch">Query_Expression_With_Fetch</a>.<br />
<a href="#row_var">Rowset_Variable</a> :=
     '@' + <a href="u-sql-identifiers.md">Unquoted_Identifier</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements    
- <a name="row_var"></a>**`Rowset_Variable`**   
  The rowset variable is the name given to the provided <a href="#qry_exp_fetch">Query_Expression_With_Fetch</a>. Note that this rowset variable is **not** containing the result of the query expression. It is a reference to the expression itself, similar to the [SQL Common-Table Expression](https://msdn.microsoft.com/library/ms175972.aspx) names or the names of functional lambda expressions in functional languages.  
  
  The name can be used in subsequent query expressions to refer to the named expression that then will be inlined.  
   
- <a name="qry_exp_fetch"></a>**`Query_Expression_With_Fetch`**   
  Is the query expression followed by an optional [`ORDER BY/OFFSET FETCH`](../USQL/order-by-and-offset-fetch-clause-u-sql.md) clause.   
  
  <table><th>Syntax U-SQL Query Expressions</th><tr><td><pre>
  Query_Expression_With_Fetch :=
       Query_Expression <a href="ORDER%20BY%20and%20OFFSET_FETCH%20Clause%20(U-SQL).md">[Order_By_Fetch_Clause]</a>.<br />     
  Query_Expression :=
       <a href="#pri_row_exp">Primary_Rowset_Expression</a>
  |    '(' Query_Expression_With_Fetch ')'
  |    <a href="Set%20Rowset%20Expressions%20(U-SQL).md">Set_Rowset_Expression</a>.
  </pre></td></tr></table>
    
  - <a name="qry_exp"></a>**`Query_Expression`**   
    Is the actual transformation expression.  A query expression can either be a primary rowset query, a query expression enclosed in parenthesis or a [set expression over two rowsets](../USQL/set-rowset-expressions-u-sql.md).   

  - <a name="pri_row_exp"></a>**`Primary_Rowset_Expression`**  
    U-SQL’s primary rowset expressions are the main rowset generating and transforming expressions of the language: The [EXTRACT](../USQL/extract-expression-u-sql.md) expression to generate a rowset from unstructured data, the [SELECT](../USQL/select-expression-u-sql.md) expression, and the [PROCESS](../USQL/process-expression-u-sql.md), [REDUCE](../USQL/reduce-expression-u-sql.md), [COMBINE](../USQL/combine-expression-u-sql.md) expressions that apply the custom-defined [user-defined operators](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-objects--udo) (UDO) to the input rowset(s) and generate a new rowset. In addition it also includes the invocation of [table-valued functions](../USQL/u-sql-table-valued-functions.md).  

    <table><th>Syntax Primary Rowset Expression</th><tr><td><pre>
    Primary_Rowset_Expression :=                                                                   
         <a href="extract-expression-u-sql.md">Extract_Expression</a>
    |    <a href="select-expression-u-sql.md">Select_Expression</a>
    |    <a href="process-expression-u-sql.md">Process_Expression</a>
    |    <a href="reduce-expression-u-sql.md">Reduce_Expression</a>
    |    <a href="combine-expression-u-sql.md">Combine_Expression</a>
    |    <a href="table-valued-function-expression-u-sql.md">Function_Call</a>
    </pre></td></tr></table>
        
    Please review the individual expressions, above, for more detailed examples.
        
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
```
@someBooks = 
    SELECT * FROM 
        ( VALUES
        ("The Book Thief", "Markus Zusak", "2005"),
        ("The Girl with the Dragon Tattoo", "Stieg Larsson", "2005"),
        ("The Silver Linings Playbook", "Matthew Quick", "2008"),
        ("Sarah's Key", "Tatiana de Rosnay", "2006")
        ) AS T(Book, Author, [Publication Year]);
        
@rowsetVariable =
    SELECT Book, Author
    FROM @someBooks;

OUTPUT @rowsetVariable
TO "/ReferenceGuide/DML/QSE/exampleA.txt"
USING Outputters.Tsv();
```

  
### See Also 
* [Data Modification Language (DML) Statements (U-SQL)](../USQL/data-modification-language-dml-statements-u-sql.md) 
* [Output Statement (U-SQL)](../USQL/output-statement-u-sql.md)  

