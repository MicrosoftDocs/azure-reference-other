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
<table><th align="left">Syntax</th><tr><td><pre>
Built_In_Analytic :=                                                                                   
      <a href="cume-dist-u-sql.md">'CUME_DIST'</a>
|     <a href="first-value-u-sql.md">'FIRST_VALUE'</a> 
|     <a href="lag-u-sql.md">'LAG'</a> 
|     <a href="last-value-u-sql.md">'LAST_VALUE'</a> 
|     <a href="lead-u-sql.md">'LEAD'</a> 
|     <a href="percentile-cont-u-sql.md">'PERCENTILE_CONT'</a> 
|     <a href="percentile-disc-u-sql.md">'PERCENTILE_DISC'</a> 
|     <a href="percent-rank-u-sql.md">'PERCENT_RANK'</a>.</pre></td></tr></table>

### See Also 
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 



