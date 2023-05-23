---
title: "System.Timestamp() (Stream Analytics)"
description: "System.Timestamp() is a system property that can be used to retrieve the event’s timestamp. "
applies_to: 
  - "Azure"


ms.service: stream-analytics
ms.topic: reference
ms.date: 04/22/2016
---
# System.Timestamp() (Stream Analytics)
  Every event at every stage of the query in Azure Stream Analytics has a timestamp associated with it. System.Timestamp() is a system property that can be used to retrieve the event’s timestamp.  
  
 Below, we describe how Azure Stream Analytics assigns timestamps to events.  
  
### **Input events timestamp**  
 Timestamp of the input event can be defined by column value (or an expression) specified in the [TIMESTAMP BY](timestamp-by-azure-stream-analytics.md) clause:  
  
```SQL  
SELECT System.Timestamp() t   
FROM input   
TIMESTAMP BY MyTimeField  
  
```  
  
 If a TIMESTAMP BY clause is not specified for a given input, arrival time of the event is used as a timestamp. For example Enqueued time of the event will be used in case of Event Hub input.  
  
### **Resulting event timestamp**  
 When computations are performed, the timestamp of the resulting event is the earliest logical time at which this result could be determined.  
  
 Let’s look at how the basic query operations in Azure Stream Analytics (filters, projections, aggregations and joins) generate the timestamps for the result.  
  
### **Projection**  
  
```SQL  
SELECT  
      Prop1,  
      Prop2,  
      Prop3 - Prop4 / 12,
      System.Timestamp() t  
FROM input  
  
```  
  
 Projections do not alter the timestamp of the event, the timestamp of the result is the same as the timestamp of the input.  
  
### **Filter**  
  
```SQL  
SELECT *  
FROM input  
WHERE prop1 > prop2  
  
```  
  
 Filters do not alter the timestamp of the event. The timestamp of the result is the same as the timestamp of the input.  
  
### **GROUP BY over time window**  
  
```SQL  
SELECT  
      userId,  
      AVG(prop1),  
      SUM(prop2),  
      System.Timestamp() t  
FROM input  
GROUP BY TumblingWindow(minute, 1), userId  
  
```  
  
 The timestamp of the result of the aggregate is the end of the time window to which this result corresponds. Please see [Windowing &#40;Azure Stream Analytics&#41;](windowing-azure-stream-analytics.md) articles describing different window types in Azure Stream Analytics.  
  
### **INNER JOIN**  
  
```SQL  
SELECT  
      System.Timestamp()  
FROM input1  
JOIN input2  
ON DATEDIFF(minute, input1, input2) BETWEEN 0 AND 10  
  
```  
  
 An inner join produces results that correspond to matching pairs of events from input1 and input2.  
  
 The event that represents the match of event e1 from input1 and e2 from input2 is timestamped by the latest of the timestamps of e1 and e2.  
  
### **LEFT OUTER JOIN**  
  
```SQL  
SELECT  
      System.Timestamp()  
FROM input1  
LEFT JOIN input2  
ON DATEDIFF(minute, input1, input2) BETWEEN -2 AND 10  
  
```  
  
 A left-outer join produces results of two types.  Some correspond to a matching pair of events from input1 and input2; others correspond to just an event from input1, and indicate that no matching event from input2 was found.  
  
 The events that represent a match (has both input1 and input2) is timestamped by the latest of the timestamps of the matching inputs (as in the case of the INNER JOIN above).  
  
 The events that represent non-matches (input2 is NULL) are timestamped by the latest logical time at which a matching input2 event could have occurred.  For instance, in the example above, it is input1’s timestamp + 10 minutes.  
  
  
