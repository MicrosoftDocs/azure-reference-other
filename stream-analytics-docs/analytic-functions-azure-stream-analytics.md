---
title: "Analytic Functions (Azure Stream Analytics) | Microsoft Docs"
description: "Lists the analytic functions supported by Stream Analytics Query Language"
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
ms.service: stream-analytics
ms.topic: reference
ms.assetid: 953c32f0-985e-46b1-b050-1a6911acb83c
caps.latest.revision: 12
ms.workload: data-services
ms.date: 06/07/2019
ms.author: mamccrea
---

# Analytic Functions (Azure Stream Analytics)
  Stream Analytics Query Language provides the following analytic functions:  
  
|||| 
|-|-|-| 
|[ISFIRST &#40;Azure Stream Analytics&#41;](isfirst-azure-stream-analytics.md)|[LAG &#40;Azure Stream Analytics&#41;](lag-azure-stream-analytics.md)|[LAST &#40;Azure Stream Analytics&#41;](last-azure-stream-analytics.md)|
|[COUNT &#40;Azure Stream Analytics&#41;](count-azure-stream-analytics.md) | [MIN &#40;Azure Stream Analytics&#41;](min-azure-stream-analytics.md) | [MAX &#40;Azure Stream Analytics&#41;](max-azure-stream-analytics.md)
| [SUM &#40;Azure Stream Analytics&#41;](sum-azure-stream-analytics.md) | [AVG &#40;Azure Stream Analytics&#41;](avg-azure-stream-analytics.md) |
|[Collect &#40;Azure Stream Analytics&#41;](collect-azure-stream-analytics.md) | [CollectTOP &#40;Azure Stream Analytics&#41;](collecttop-azure-stream-analytics.md)| [TopOne &#40;Azure Stream Analytics&#41;](topone-azure-stream-analytics.md)|
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
  
  
