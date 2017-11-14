---
title: "SELECT Expression (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-16"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 0e51f64f-814a-428d-84d1-5001451e5b16
caps.latest.revision: 18
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# SELECT Expression (U-SQL)
The SELECT expression is the transformation and query workhorse. It basically follows the standard SQL SELECT expression.  
  
The logical processing flow of a SELECT expression is as follows: First the rowsets specified in the SELECT’s FROM clause will be combined into the SELECT expression’s rowset. Then the optional WHERE clause’s filter conditions are applied onto the rowset. The [GROUP BY](group-by-and-having-clauses-u-sql.md) clause is then producing groups of rows, optionally filtered with the HAVING clause. The [SELECT clause](select-clause-u-sql.md) then projects the specified columns and allows aggregating the grouped data as well as transforming the selected data. 
  
Note that unlike in other systems, where a SELECT clause can output results to the user at any time, U-SQL’s current batch-mode centric execution model never outputs a SELECT result directly. Instead, a SELECT expression is always assigned to a rowset expression variable and in the end the script results needs to either be output into files or inserted into tables.  

For ordered output, use the [ORDER BY](output-statement-u-sql.md#OBOFC) clause on the [OUTPUT](output-statement-u-sql.md) statement.


<table><th>Syntax</th><tr><td><pre>
Select_Expression :=                                                                                     
    <a href="select-clause-u-sql.md">Select_Clause</a><br /> 
<a href="from-clause-u-sql.md">    Select_From_Clause</a><br />  
<a href="where-clause-u-sql.md">    [Where_Clause]</a><br />  
<a href="group-by-and-having-clauses-u-sql.md">    [Group_By_Clause]</a><br />  
<a href="order-by-and-offset-fetch-clause-u-sql.md">    [Order_By_Fetch_Clause]</a>.
</pre></td></tr></table>
  
### Semantics of Syntax Elements    
-   [**`Select_Clause`**](select-clause-u-sql.md)  
    The `SELECT` clause specifies the resulting structure and values of the rowset of the `SELECT` expression.  
  
-   [**`Select_From_Clause`**](from-clause-u-sql.md)  
    The `FROM` clause specifies the input rowsets to the `SELECT` expression and how the rowsets are being combined into the `SELECT` expression’s rowset.  
  
-   [**`Where_Clause`**](where-clause-u-sql.md)   
    The optional `WHERE` clause specifies the filter conditions of the `SELECT` expression which will reduces the rows that are being produced as a result.  
  
-   [**`Group_By_Clause`**](group-by-and-having-clauses-u-sql.md)    
    The optional `GROUP BY` clause groups the rows based on the provided expression list into groups that then can be aggregated over with the built-in and user-defined aggregator functions.  
  
 
### See Also 
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md) 
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)   
* [Output Statement (U-SQL)](output-statement-u-sql.md) 
* [ORDER BY and OFFSET/FETCH Clause (U-SQL)](order-by-and-offset-fetch-clause-u-sql.md) 
 
