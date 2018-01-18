---
title: "LAG (Azure Stream Analytics) | Microsoft Docs"
description: "The LAG analytic operator allows one to look up the “previous” event in an event stream, within certain constraints."
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: 37ff8d85-b679-430a-bab6-6f8f313e7282
caps.latest.revision: 13
ms.workload: data-services
ms.date: 12/03/2017
ms.author: sngun
---
# LAG (Azure Stream Analytics)
The LAG analytic operator allows one to look up the “previous” event in an event stream, within certain constraints. It is very useful for computing the rate of growth of a variable, detecting when a variable crosses a threshold, or when a condition starts or stops being true. 
  
In Stream Analytics, the scope of LAG (that is, how far back in history from the current event it needs to look) is always limited to a finite time interval, using the LIMIT DURATION clause. LAG can optionally be limited to only consider events that match the current event on a certain property or condition using the PARTITION BY and WHEN clauses. LAG is not affected by predicates in WHERE clause, join conditions in JOIN clause, or grouping expressions in GROUP BY clause of the current query.
  
 **Syntax**  
  
```SQL  
LAG(<scalar_expression >, [<offset >], [<default>])  
     OVER ([PARTITION BY <partition key>] LIMIT DURATION(<unit>, <length>) [WHEN boolean_expression])
  
```  
  
 For instance:  
  
```SQL  
LAG(reading) OVER (LIMIT DURATION(hour, 3))  
LAG(name, 2, “none such”) OVER (PARTITION BY userId LIMIT DURATION(minute, 2))  
```  
  
## Arguments  
 **scalar_expression**  
  
 The value to be returned based on the specified offset. It is either an expression of any type that returns a single (scalar) value or the wildcard expression ‘*’. For ‘\*’ the entire event according to the specified offset will be returned and will be contained in the result event (nested record).  
scalar_expression cannot contain other analytic functions or external functions.  
  
 **offset**  
  
 The number of events back from the current event from which to obtain a value. If not specified, the default is 1. offset must be an integer greater than or equal to zero. Events are processed in temporal order. If there are several events with the same time stamp events are processed in the order of arrival.  
  
 **default**  
  
 The value to return when there is no event at the specified offset. If a default value is not specified, NULL is returned. ‘No event at the specified offset’ can be the case 1) if the number of corresponding events seen so far is smaller than the specified offset or 2) if the event at the  specified offset is timed out according to the specified limit_duration_clause 3) events exist but do not match boolean condition specified in the when_clause.  
  
 If the event at the specified offset exists and the value of scalar_expression is NULL then NULL  
is returned. default can be a column, subquery, or other expression, but it cannot contain other  
analytic functions or external functions. default must have the exact same type as  
scalar_expression.  
  
 **OVER ( [ partition_by_clause ] limit_duration_clause [when_clause])**  
  
 **partition_by_clause** PARTITION BY \<partition key> clause requests that only events whose value of  
\<partition key> is the same as that of the current event be considered. For instance,  
  
```  
LAG(reading) OVER (PARTITION BY sensorId LIMIT DURATION(hour, 1))  
```  
  
 will return the previous reading of the same sensor as the current event (if such occurred within the preceding 1 hour).  
  
 **limit_duration clause** DURATION(\<unit>, \<length>)  
  
 Specifies how much of the history from the current event must be considered. See DATEDIFF for a detailed description of supported units and their abbreviations. If not enough matching events are found within the DURATION interval, the \<default> value is returned.  
  
 **when_clause**  
 Specifies boolean condition for the events to be considered in LAG computation. If not enough matching events are found within the DURATION interval, the \<default> value is returned. The when_clause is optional.  
  
## Return Types  
 The data type of the specified scalar_expression. NULL is returned if scalar_expression  
  
## General Remarks  
 LAG is nondeterministic. Events are processed in temporal order. If there are several events with the same time stamp events are processed in the order of arrival.  
  
## Examples  
 Compute the rate of growth, per sensor:  
  
```SQL  
SELECT sensorId,  
       growth = reading –  
                        LAG(reading) OVER (PARTITION BY sensorId LIMIT DURATION(hour, 1))  
FROM input  
  
```  
  
 Find previous not-null sensor reading’:  
  
```SQL  
SELECT  
     sensorId,  
     LAG(reading) OVER (PARTITION BY sensorId LIMIT DURATION(hour, 1) WHEN reading IS NOT NULL)  
     FROM input  
  
```  
  
 Determine when a variable crosses a threshold:  
  
```SQL  
SELECT
    sensorId, reading
FROM input
WHERE
    devicetype = 'thermostat'
    AND reading > 100
    AND LAG(reading) OVER (PARTITION BY sensorId LIMIT DURATION(hour, 1) WHEN devicetype = 'thermostat') <= 100
  
```  
  
## See Also  
 [ISFIRST &#40;Azure Stream Analytics&#41;](isfirst-azure-stream-analytics.md)   
 [LAST &#40;Azure Stream Analytics&#41;](last-azure-stream-analytics.md)  
  
  