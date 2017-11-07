---
title: "U-SQL SELECT Selecting from CROSS APPLY and OUTER APPLY | Microsoft Docs"
ms.custom: ""
ms.date: "2017-04-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b5479228-7c9f-40c7-9bac-f24a582319a0
caps.latest.revision: 15
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL SELECT Selecting from CROSS APPLY and OUTER APPLY
Often when processing some more complex value in a column, such as a byte array, a string, a MAP, ARRAY, JSON or XML document, one would like to extract more than just one value, such as a whole rowset of information per column value.  
  
U-SQL provides the CROSS APPLY and OUTER APPLY operator which evaluates the rowset generating expressions on the right side against each row and its individual column cells of the rowset on the left. The result is the combination of the columns of both rowsets where the values of the left rowset get repeated for each result of the right rowset expression.  
  
When CROSS APPLY is specified, no rows are produced for the row of the left rowset when the right-side rowset expression returns an empty rowset for that row.  
  
When OUTER APPLY is specified, one row is produced for each row of the left rowset even when the right-side rowset expression returns an empty rowset for that row.  
  
This operator is also known as LATERAL in other SQL dialects.  
  
Because implementing a fully generic CROSS APPLY in a scale-out query processor is a difficult problem, U-SQL supports only a few special types of expressions that can be applied to a rowset source. The first expression type uses the built-in [EXPLODE()](../USQL/explode-u-sql.md) expression and the second one is an expression that provides a user-defined operator called an [Applier](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-applier).  
  
<table><th>Syntax</th><tr><td><pre>
Apply_Expression :=                                                                                      
    <a href="#row_src">Rowset_Source</a> <a href="#aply_op">Apply_Operator</a> <a href="#expl_exp">Explode_Expression</a>  
|   <a href="#row_src">Rowset_Source</a> <a href="#aply_op">Apply_Operator</a> <a href="#apl_exp">Applier_Expression</a>
|   <a href="#row_src">Rowset_Source</a> <a href="#aply_op">Apply_Operator</a> <a href="u-sql-select-selecting-from-the-values-table-value-constructor.md">Table_Value_Constructor_Expression</a> <a href="u-sql-select-selecting-from-the-values-table-value-constructor.md">Derived_Table_Alias</a>
</pre></td></tr></table>
   
### Semantics of Syntax Elements    
-   <a name="row_src"></a>**`Rowset_Source`**  
    Identifies the input on which the explode or applier expression is being applied row-by-row. For more details on the rowset source see U-SQL SELECT [FROM Clause](../USQL/from-clause-u-sql.md).  
  
- <a name="aply_op"></a>**`Apply_Operator`**   
Is specifying the type of the apply operation: `INNER` or `OUTER APPLY`.  
  
  <table><th>Syntax</th><tr><td><pre>
Apply_Operator :=                                                                                   
      'CROSS' 'APPLY'  
|     'OUTER' 'APPLY'.  
</pre></td></tr></table>
      
    When CROSS APPLY is specified, no rows are produced for the row of the left rowset when the right-side rowset expression returns an empty rowset for that row.  
  
    When OUTER APPLY is specified, one row is produced for each row of the left rowset even when the right-side rowset expression returns an empty rowset for that row.  
 
-   <a name="expl_exp"></a>**`Explode_Expression`**  
    Turns an instance of type [SQL.ARRAY](../USQL/complex-built-in-u-sql-types.md)  or [SQL.MAP](../USQL/complex-built-in-u-sql-types.md) into a rowset where each item or key/value pair respectively is mapped into a row. For more details see  [EXPLODE (U-SQL)](../USQL/explode-u-sql.md).
  
-   <a name="apl_exp"></a>**`Applier_Expression`**  
    Is a U-SQL expression that returns an instance of an IApplier user-defined operator, that in turn takes each row of the input rowset into 0 to n rows of the specified schema of the applier clause. For more details see [U-SQL Using APPLY with an Applier UDO](../USQL/u-sql-using-apply-with-an-applier-udo.md).  
    
### See Also 
* [Query Statements and Expressions (U-SQL)](../USQL/query-statements-and-expressions-u-sql.md)
* [SELECT Expression (U-SQL)](../USQL/select-expression-u-sql.md) 
* [FROM Clause (U-SQL)](../USQL/from-clause-u-sql.md) 
* [Output Statement (U-SQL)](../USQL/output-statement-u-sql.md)  
* [U-SQL Programmability Guide: User-Defined Applier](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-applier)

