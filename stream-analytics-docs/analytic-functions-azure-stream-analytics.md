---
title: "Analytic Functions (Azure Stream Analytics)"
description: "Lists the analytic functions supported by Stream Analytics Query Language"
applies_to: 
  - "Azure"
ms.service: stream-analytics
ms.topic: reference
ms.date: 06/07/2019
---

# Analytic Functions (Azure Stream Analytics)
  Stream Analytics Query Language provides the following analytic functions:  
  
|Analytic functions| ...| ...| 
|-|-|-| 
|[ISFIRST &#40;Azure Stream Analytics&#41;](isfirst-azure-stream-analytics.md)|[LAG &#40;Azure Stream Analytics&#41;](lag-azure-stream-analytics.md)|[LAST &#40;Azure Stream Analytics&#41;](last-azure-stream-analytics.md)|
|[AnomalyDetection_SpikeAndDip](anomalydetection-spikeanddip-azure-stream-analytics.md)|[AnomalyDetection_ChangePoint](anomalydetection-changepoint-azure-stream-analytics.md)||
  
Note that analytic functions in Stream Analytics query language, unlike in T-SQL, are evaluated first. In Stream Analytics query language:
* Analytic functions can be used in any place in the query that a scalar function is allowed. For example, you can use analytic functions in **WHERE** clause, **JOIN** clause, or **GROUP BY** clause.
* Analytic function computations are performed over all the input events of the current query input, optionally you can limit analytic function to only consider events that match the **partition_by_clause** and **when_clause**.
* Analytic functions are not affected by predicates in **WHERE** clause, join conditions in **JOIN** clause, or grouping expressions in **GROUP BY** clause of the current query.
  
## See Also  
 [Built-In Functions](built-in-functions-azure-stream-analytics.md)   
 [Aggregate Functions](aggregate-functions-azure-stream-analytics.md)   
 [Array Functions](array-functions-stream-analytics.md)   
 [Conversion Functions](conversion-functions-azure-stream-analytics.md)   
 [Date and Time Functions](date-and-time-functions-azure-stream-analytics.md)   
 [Mathematical Functions](mathematical-functions-azure-stream-analytics.md)   
 [Record Functions](record-functions-azure-stream-analytics.md)   
 [String Functions](string-functions-azure-stream-analytics.md)  
  
  
