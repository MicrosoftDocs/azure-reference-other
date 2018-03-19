---
title: "Ranking Functions (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 789e6e92-7959-483c-9a69-eef3a76c83ee
caps.latest.revision: 11
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# Ranking Functions (U-SQL)
U-SQL provides some built-in SQL-based ranking functions that return a ranking value for each row in a partition. Depending on the function that is used, some rows might receive the same value as other rows. Ranking functions are nondeterministic. 

In U-SQL, ranking functions can only be used in the following syntactic contexts: 

* As a window function in a [windowing expression](over-expression-u-sql.md) with the [OVER](over-expression-u-sql.md) clause where it will calculate the value for each window partition. 

Ranking functions cannot be nested. 

U-SQL provides the following built-in ranking functions (follow the links for more information): 

|Ranking Function|Description|
|------|----|
|[DENSE_RANK](dense-rank-u-sql.md)|Returns the rank of rows within the partition of a window, without any gaps in the ranking. |
|[NTILE](ntile-u-sql.md)|Returns the number of the group to which the row belongs from among the groups that the windowing function has distributed the rows using an ordered partition.|
|[RANK](rank-u-sql.md) |Returns the rank of each row within the window. |
|[ROW_NUMBER ](row-number-u-sql.md) | Returns the sequential number of a row within a window.|
 
### See Also 
* [Built-in Functions (U-SQL)](built-in-functions-u-sql.md)  
* [OVER Expression (U-SQL)](over-expression-u-sql.md)  






