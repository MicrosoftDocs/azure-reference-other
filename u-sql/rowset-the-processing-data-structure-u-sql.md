---
title: "Rowset The Processing Data Structure (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 46d8e867-95ea-458a-bb14-ccd155adb71a
caps.latest.revision: 13
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Rowset: The Processing Data Structure (U-SQL)
Since U-SQL is a SQL based language, its main processing data structure is a rowset. Thus any data that needs to be processed needs to be transformed into a rowset first and then combined with other rowsets and transformed with U-SQL query expressions. Here are some U-SQL specific aspects of its rowsets:    
1.  A U-SQL rowset flows through the U-SQL expression flow and only gets persisted with an explicit insertion into a table using an [INSERT](insert-u-sql.md) or [CREATE TABLE](create-table-u-sql-overview.md) AS statement.  
  
     Note that the variables assigned to rowset expressions are not materializing a rowset. The variables represent names for the rowset expressions.    
  
2.  A rowset is unordered. This means any order among the rows cannot be relied upon in a subsequent expression.  This also means that the [ORDER BY](order-by-and-offset-fetch-clause-u-sql.md) clause is only supported in contexts where order is usable. The fact that rowsets are unordered also provides the ability to scale out the processing of a rowset across as many parallel processing nodes as needed.   
    
3.  U-SQL rows can contain up to 4 MB of data per row.   

4.  Each rowset column is named with either a [quoted or unquoted identifier](u-sql-identifiers.md) and is of one of the supported [built-in U-SQL column types](built-in-u-sql-types.md).    

### See Also
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md) 
