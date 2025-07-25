---
title: "Time Management"
description: "Stream Analytics provides language constructs to deal with the temporal aspects of the data."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# Time Management
:white_check_mark: Azure Stream Analytics

Query language extends SQL syntax to enable complex computations over streams of events. Stream Analytics provides language constructs to deal with the temporal aspects of the data. For example, it is possible to assign custom timestamps to the stream events, specify time window for aggregations, specify allowed time difference between two streams of data for JOIN operation, etc.  
 
 All time handling operations are in UTC.
 
 
|Item|Summary|  
|----------|-------------|  
|[System.Timestamp()](system-timestamp-stream-analytics.md)|System.Timestamp() is a system property that can be used to retrieve the event’s timestamp.|  
|[TIMESTAMP BY](timestamp-by-azure-stream-analytics.md)|The TIMESTAMP BY clause allows specifying custom timestamp values.|  
|[Time Skew Policies](time-skew-policies-azure-stream-analytics.md)|Policies for Out of Order and Late Arrival Events.|  
|[Aggregate functions](aggregate-functions-azure-stream-analytics.md) over [time window](windowing-azure-stream-analytics.md)|Aggregate functions are used to perform a calculation on a set of values from a time window and return a single value.|  
|[DATEDIFF in JOIN predicate](join-azure-stream-analytics.md)|Specify time boundaries for JOIN operations|  
|[Date and Time functions](date-and-time-functions-azure-stream-analytics.md)|Stream Analytics provides a variety of date and time functions for use.|  
  
## See Also  
 [Built-in Functions](built-in-functions-azure-stream-analytics.md)   
 [Data Types](data-types-azure-stream-analytics.md)   
 [Event Delivery Guarantees&#40;Azure Stream Analytics&#41;](event-delivery-guarantees-azure-stream-analytics.md)  
  
  
