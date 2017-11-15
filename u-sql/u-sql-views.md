---
title: "U-SQL Views | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 3a5df149-b79b-474b-bfee-ae9fe98e3218
caps.latest.revision: 14
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Views
U-SQL supports creating and dropping views over rowsets.  
  
### View DDL Statements
<table><th align="left">Syntax</th><tr><td><pre>
View_DDL_Statement :=                                                                                    
     <a href="create-view-u-sql.md">Create_View_Statement</a>
|    <a href="drop-view-u-sql.md">Drop_View_Statement.</a>
</pre></td></tr></table>
 
In U-SQL Views will be inlined into the expression where they are being referenced and thus are similar to the rowset expression variables, which the difference that the variables only exist for the duration of a script while a view will be made available through the metadata catalog to other scripts.  
  
Unlike tables that can be created with a query expressions, views are not copying the data but are always executed against the data over which the view is defined. This avoids copying the data and thus will always pick up the latest data while costing the execution of the query expression in every query.  
  
U-SQL also provides parameterized views through [table-valued functions](../u-sql/u-sql-functions.md).  
  
### See Also    
- [CREATE VIEW (U-SQL)](../u-sql/create-view-u-sql.md)
- [DROP VIEW (U-SQL)](../u-sql/drop-view-u-sql.md)
- [U-SQL Functions](../u-sql/u-sql-functions.md)
  

