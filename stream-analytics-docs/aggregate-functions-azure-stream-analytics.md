---
title: "Aggregate Functions"
description: "Aggregate functions perform a calculation on a set of values and return a single value. Except for the COUNT function, aggregate functions ignore null values."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# Aggregate Functions
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

Aggregate functions perform a calculation on a set of values and return a single value. Except for the COUNT function, aggregate functions ignore null values. Aggregate functions are frequently used with the GROUP BY clause of the SELECT statement.  
  
All aggregate functions are deterministic. This means aggregate functions return the same value any time that they are called by using a specific set of input values.  
  
Aggregate functions can be used as expressions only in the following:  
  
- The select list of a SELECT statement (either a subquery or an outer query).  
  
- A HAVING clause.  
  
 Stream Analytics Query Language provides the following aggregate functions:  
  
|Aggregate functions | ... | ...|  
|-|-|-|  
|[AVG](avg-azure-stream-analytics.md)|[COUNT](count-azure-stream-analytics.md)|[Collect](collect-azure-stream-analytics.md)|
|[CollectTOP](collecttop-azure-stream-analytics.md)|[MAX](max-azure-stream-analytics.md)|[MIN](min-azure-stream-analytics.md)|
|[Percentile_Cont](percentile-cont-azure-stream-analytics.md)  | [Percentile_Disc](percentile-disc-azure-stream-analytics.md) |[STDEV](stdev-azure-stream-analytics.md)|
|[STDEVP](stdevp-azure-stream-analytics.md)|[SUM](sum-azure-stream-analytics.md)| [TopOne](topone-azure-stream-analytics.md)|
|[VAR](var-azure-stream-analytics.md)|[VARP](varp-azure-stream-analytics.md)|
  
## See Also  

 [Built-In Functions](built-in-functions-azure-stream-analytics.md)   
 [Analytic Functions](analytic-functions-azure-stream-analytics.md)   
 [Array Functions](array-functions-stream-analytics.md)   
 [Conversion Functions](conversion-functions-azure-stream-analytics.md)   
 [Date and Time Functions](date-and-time-functions-azure-stream-analytics.md)   
 [Mathematical Functions](mathematical-functions-azure-stream-analytics.md)   
 [Record Functions](record-functions-azure-stream-analytics.md)   
 [String Functions](string-functions-azure-stream-analytics.md)  
  
  
