---
title: "Analytic Functions (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 671f0615-b52e-4192-9f0f-487b8ade8882
caps.latest.revision: 10
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# Analytic Functions (U-SQL)
U-SQL supports a set of SQL-based analytic functions that compute an aggregate value based on a group of rows. However, unlike [aggregate functions](aggregate-functions-u-sql.md), they can return multiple rows for each group. You can use analytic functions to compute moving averages, running totals, percentages or top-N results within a group.  

In U-SQL, analytics functions can only be used in the following syntactic contexts: 

* As a window function in a [windowing expression](over-expression-u-sql.md) with the [OVER](over-expression-u-sql.md) operator where it will calculate the value for each window partition. 

Some of the analytics functions are type-polymorphic, meaning that they can operate on many different input types and return potentially different types based on their input type.  

Analytics functions cannot be nested. 

U-SQL provides the following built-in analytic functions: 

|Analytic Function|Description|
|------|----|
|[CUME_DIST](cume-dist-u-sql.md)|Calculates the cumulative distribution of a value in a group of values.|
|[FIRST_VALUE](first-value-u-sql.md)|Returns the first value in an ordered set of values provided by the windowing expression. |
|[LAG](lag-u-sql.md)|Provides access to a row at a given physical offset that comes before the current row.|
|[LAST_VALUE](last-value-u-sql.md)|Returns the last value in an ordered set of values provided by the windowing expression. |
|[LEAD](lead-u-sql.md)|Provides access to a row at a given physical offset that follows the current row. |
|[PERCENTILE_CONT](percentile-cont-u-sql.md)|Calculates a percentile based on a continuous distribution of the values in the window.|
|[PERCENTILE_DISC](percentile-disc-u-sql.md)|Computes a specific percentile for sorted values in the specified window based on a discrete distribution of the column values.|
|[PERCENT_RANK](percent-rank-u-sql.md)|Calculates the relative rank of a row within a group of rows specified by the windowing expression.|
<br />

## See Also 
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)
