---
title: "ISFIRST (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-20"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: e905fd1b-94df-44ad-822f-7c92dc6acfcc
caps.latest.revision: 11
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# ISFIRST (Azure Stream Analytics)
Returns 1 if the event is the first event within a given duration, or 0 otherwise. ISFIRST is not affected by predicates in WHERE clause, join conditions in JOIN clause, or grouping expressions in GROUP BY clause of the current query.
  
 **Syntax**  
  
```  
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
  
## Examples  
 Indicate whether a sensor reading event is the first within 10 minutes:  
  
```  
SELECT  
       reading,  
       ISFIRST(mi, 10) as first  
FROM Input  
```  
  
 Indicate whether an event is the first within 10 minute intervals per deviceid:  
  
```  
SELECT  
       deviceid,  
       reading,  
       ISFIRST(mi, 10) OVER (PARTITION BY deviceid) as first  
FROM Input  
```  
  
 Indicate whether an event is the first event with value greater than 50 within 10 minute intervals  
per deviceid:  
  
```  
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
  
  