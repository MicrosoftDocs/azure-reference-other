---
title: "Aggregate Functions (Azure Stream Analytics)"
description: "Aggregate functions perform a calculation on a set of values and return a single value. Except for the COUNT function, aggregate functions ignore null values."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# Aggregate Functions (Azure Stream Analytics)

Aggregate functions perform a calculation on a set of values and return a single value. Except for the COUNT function, aggregate functions ignore null values. Aggregate functions are frequently used with the GROUP BY clause of the SELECT statement.  
  
All aggregate functions are deterministic. This means aggregate functions return the same value any time that they are called by using a specific set of input values.  
  
Aggregate functions can be used as expressions only in the following:  
  
- The select list of a SELECT statement (either a subquery or an outer query).  
  
- A HAVING clause.  
  
 Stream Analytics Query Language provides the following aggregate functions:  
  
|Aggregate functions | ... | ...|  
|-|-|-|  
|[AVG &#40;Azure Stream Analytics&#41;](avg-azure-stream-analytics.md)|[COUNT &#40;Azure Stream Analytics&#41;](count-azure-stream-analytics.md)|[Collect &#40;Azure Stream Analytics&#41;](collect-azure-stream-analytics.md)|
|[CollectTOP &#40;Azure Stream Analytics&#41;](collecttop-azure-stream-analytics.md)|[MAX &#40;Azure Stream Analytics&#41;](max-azure-stream-analytics.md)|[MIN &#40;Azure Stream Analytics&#41;](min-azure-stream-analytics.md)|
|[Percentile_Cont &#40;Azure Stream Analytics&#41;](percentile-cont-azure-stream-analytics.md)  | [Percentile_Disc &#40;Azure Stream Analytics&#41;](percentile-disc-azure-stream-analytics.md) |[STDEV &#40;Azure Stream Analytics&#41;](stdev-azure-stream-analytics.md)|
|[STDEVP &#40;Azure Stream Analytics&#41;](stdevp-azure-stream-analytics.md)|[SUM &#40;Azure Stream Analytics&#41;](sum-azure-stream-analytics.md)| [TopOne &#40;Azure Stream Analytics&#41;](topone-azure-stream-analytics.md)|
|[VAR &#40;Azure Stream Analytics&#41;](var-azure-stream-analytics.md)|[VARP &#40;Azure Stream Analytics&#41;](varp-azure-stream-analytics.md)|
  
## See Also  

 [Built-In Functions](built-in-functions-azure-stream-analytics.md)   
 [Analytic Functions](analytic-functions-azure-stream-analytics.md)   
 [Array Functions](array-functions-stream-analytics.md)   
 [Conversion Functions](conversion-functions-azure-stream-analytics.md)   
 [Date and Time Functions](date-and-time-functions-azure-stream-analytics.md)   
 [Mathematical Functions](mathematical-functions-azure-stream-analytics.md)   
 [Record Functions](record-functions-azure-stream-analytics.md)   
 [String Functions](string-functions-azure-stream-analytics.md)  
  
  
