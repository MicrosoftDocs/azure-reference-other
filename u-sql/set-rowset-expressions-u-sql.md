---
title: "Set Rowset Expressions (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-16"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 008e74a0-3dab-44cc-9d44-f7ec788a61e7
caps.latest.revision: 17
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Set Rowset Expressions (U-SQL)
Set expressions allow to intersect two rowsets, to union them or to subtract one from the other. A set expression can be a top-level [U-SQL Query expression](../USQL/query-statements-and-expressions-u-sql.md).  
  
<table><th align="left">Syntax</th><tr><td><pre>
Set_Rowset_Expression :=                                                                                 
     <a href="EXCEPT%20Expression%20(U-SQL).md">Except_Expression</a>
|    <a href="INTERSECT%20Expression%20(U-SQL).md">Intersect_Expression</a>
|    <a href="UNION%20and%20OUTER%20UNION%20Expression%20(U-SQL).md">Union_Expression</a>.
</pre></td></tr></table>

### See Also  
* [Query Statements and Expressions (U-SQL)](../USQL/query-statements-and-expressions-u-sql.md)
* [EXCEPT Expression (U-SQL)](../USQL/except-expression-u-sql.md)
* [INTERSECT Expression (U-SQL)](../USQL/intersect-expression-u-sql.md)
* [UNION and OUTER UNION Expression (U-SQL)](../USQL/union-and-outer-union-expression-u-sql.md)

