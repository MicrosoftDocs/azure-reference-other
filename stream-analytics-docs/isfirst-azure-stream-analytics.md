---
title: "ISFIRST (Azure Stream Analytics)"
description: "Returns 1 if the event is the first event within a given duration, or 0 otherwise."
applies_to: 
  - "Azure"


ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# ISFIRST (Azure Stream Analytics)

Returns 1 if the event is the first event within a given fixed interval, or 0 otherwise. The intervals are aligned the same way as tumbling windows (see [Tumbling Window](tumbling-window-azure-stream-analytics.md)). ISFIRST is not affected by predicates in WHERE clause, join conditions in JOIN clause, or grouping expressions in GROUP BY clause of the current query.
).  
  
 ## Syntax  
  
```SQL  
ISFIRST ( timeunit  , duration )   
    [ OVER ( [PARTITION BY partition_by_expression] [WHEN when_expression]) ]  
  
```  
  
## Arguments  
 **timeunit**  
  
 Is the unit of time for the duration. The following table lists all valid time unit values --- both full  
names and abbreviations may be used in the query.  
  
|Timeunit|Abbreviations|  
|--------------|-------------------|  
|day|dd, d|  
|hour|hh|  
|minute|mi, n|  
|second|ss, s|  
|millisecond|ms|  
|microsecond|mcs|  
  
 **duration**  
  
 A big integer which specifies the number of timeunits in the interval. For instance,  
ISFIRST(minute, 15) will look at 15-minute intervals. The start times of the intervals are  
aligned in the same way as in tumbling windows (see [Tumbling Window &#40;Azure Stream Analytics&#41;](tumbling-window-azure-stream-analytics.md)).  
  
 **[ OVER ( partition_by_clause [when_clause]) ]**  
  
 The OVER clause specifies the subset of the events among which this event is ranked:  
  
 **PARTITION BY partition_by_expression** clause divides the result set produced by the FROM  
clause into partitions to which the function is applied. In other words, each event is compared  
only to such other events that share its value of **partition_by_expression**. If not specified, each  
event is ranked with respect to all other events within the time interval.  
  
 **WHEN when_expression** clause specifies a boolean condition for the events to be considered.  
In other words, each event is only ranked compared to such other events that satisfy  
**when_expression**. If the event itself does not satisfy **when_expression**, the function returns 0.  
The WHEN clause is optional.  
  
## Return Types  
 bigint (either ‘1’ or ‘0’ representing ‘true’ or ‘false’ respectively)  
  
## General Remarks  
ISFIRST is nondeterministic. Events are processed in temporal order. If there are several events with the same time stamp events are processed in the order of arrival.
 
Applying ISFIRST on the result set of a [windowing function](windowing-azure-stream-analytics.md) may produce unexpected results. Windowing functions alter the timestamp of events, as every window operation outputs event at the end of the window. The current timestamp of an event can be accessed with [system.timestamp()](system-timestamp-stream-analytics.md), after a window operation it will differ from the original event time attribute. If ISFIRST can't be moved before the window operation, consider using [CollectTop](collecttop-azure-stream-analytics.md), ordering by the original event time.
  
## Examples  
 Indicate whether a sensor reading event is the first within 10 minute tumbling intervals:  
  
```SQL  
SELECT  
       reading,  
       ISFIRST(mi, 10) as first  
FROM Input  
```  
  
 Indicate whether an event is the first within 10 minute tumbling intervals per deviceid:  
  
```SQL  
SELECT  
       deviceid,  
       reading,  
       ISFIRST(mi, 10) OVER (PARTITION BY deviceid) as first  
FROM Input  
```  
  
 Indicate whether an event is the first event with value greater than 50 within 10 minute tumbling intervals  
per deviceid:  
  
```SQL  
SELECT
       deviceid,
       reading,
       ISFIRST(mi, 10) OVER (PARTITION BY deviceid WHEN reading > 50 AND devicetype = 'thermostat') as firstAbove,
       ISFIRST(mi, 10) OVER (PARTITION BY deviceid WHEN reading < 50 AND devicetype = 'thermostat') as firstUnder
FROM Input
WHERE
       devicetype = 'thermostat'
```  
  
## See Also  
 [LAG &#40;Azure Stream Analytics&#41;](lag-azure-stream-analytics.md)   
 [LAST &#40;Azure Stream Analytics&#41;](last-azure-stream-analytics.md)  
  
  
