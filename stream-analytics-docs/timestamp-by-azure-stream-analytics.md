---
title: "TIMESTAMP BY (Azure Stream Analytics)"
description: The TIMESTAMP BY clause allows specifying custom timestamp values.
ms.service: stream-analytics
ms.topic: reference
ms.date: 09/24/2020
---
# TIMESTAMP BY (Azure Stream Analytics)

All data stream events have a timestamp associated with them. By default, events from Event Hub and IoT Hub are timestamped based on when the event was received by the Event Hub or IoT Hub; events from Blob storage are timestamped by the blob's last modified time. The timestamp of an event doesn't change if you re-start or re-run your job. 

Many streaming applications require using the exact timestamp that an event occurred, rather than the arrival time. For example, in a Point of Sales application one may need event timestamps corresponding to the time a payment was logged, rather than the time a payment event reaches the event ingestion service. Additionally, geo-distributed systems and network latencies may contribute to unpredictable arrival times, making the use of an application time more reliable in a streaming application. For these cases, the TIMESTAMP BY clause allows specifying custom timestamp values. The value can be any field from the event payload or expression of type **DATETIME**. String values conforming to any of **ISO 8601** formats are also supported.  
  
Note that using a custom timestamp (TIMESTAMP BY clause) may cause Azure Stream Analytics to ingest events out of order with respect to their timestamps for two reasons:
- Individual event producers may have different (and skewed) system clocks. 
- Events from individual event producers may be delayed in transit, for example, by network unavailability at producer's site. 

While the disorder between event producers may be large, the disorder within the events from a single producer is generally small or even non-existent. In case a query only processes data from each event producer independently, handling events from each producer in its own timeline is more efficient than managing time skews between producers. Azure Stream Analytics supports substreams by specifying OVER \<over spec> sub-clause to enable processing of events in independent timelines. See 'OVER clause interacts with event ordering' for the impact the use of the OVER clause has on the processing of the job. 
  
## Syntax

```SQL   
TIMESTAMP BY scalar_expression [OVER <over spec> ]  
      
<over spec> ::= 
      { column_name | expression } [,...n ]  
```  

## Remarks

### Retrieving event timestamp 

Event timestamp can be retrieved in the SELECT statement in any part of the query using System.Timestamp() property. 

### OVER clause interacts with event ordering

When the OVER clause is used, several aspects of event processing by Azure Stream Analytics are modified: 

1. Maximum out-of-order tolerance is applied within a single value tuple of \<over spec>. That is, an event is considered out of order only if it arrives too much out of order with respect to other events from the same event producer. 

   For instance, a value of '0' can be used if events from the same event producer are always ordered and will result in immediate processing. On the other hand, using large values here will introduce processing delays, while waiting for the out-of-order events to assemble. 
  
 2. Maximum late-arrival tolerance is applied globally (as if OVER was not used). That is, an event is considered late-arriving if its chosen timestamp (in the TIMESTAMP BY clause) is too far back from its arrival time. 

    Note that using large values here will not introduce processing delays and events will still be processed immediately (or according to the maximum out-of-order tolerance). A value of several days is not unreasonable. However, using exceptionally long values may have an impact on the amount of memory required to process the job. 
   
3. Output events for each event producer are generated as they are computed, which means that the output events may have out-of-order timestamps; however, they will be in-order within a single value tuple of \<over spec>. 
      

#### Limitations and Restrictions  
TIMESTAMP BY OVER clause has the following limitations of usage: 

1. TIMESTAMP BY OVER clause must be used for all inputs of the query or not used for any of them.

2. TIMESTAMP BY OVER clause is only supported with fully parallel jobs or single partition jobs.

3. If input stream has more than one partition, the OVER clause must be used together with the PARTITION BY clause. The PartitionId column must be specified as part of TIMESTAMP BY OVER columns.

4. If TIMESTAMP BY OVER clause is used, column names from the clause must be used as grouping key in GROUP BY statements and in all JOIN predicates when joining between streams.

5. Columns created in a SELECT statement or in any other query clauses cannot be used in the TIMESTAMP BY clause, a field from the input payload must be used. For example, the result of a [CROSS APPLY](apply-azure-stream-analytics.md) cannot be used as the target value of the TIMESTAMP BY. However, you can use one Azure Stream Analytics job that performs the CROSS APPLY, and use a second job to perform the TIMESTAMP BY.

6.  System.Timestamp() cannot be used in TIMESTAMP BY, since TIMESTAMP BY is what establishes the value of System.Timestamp().

  
## Examples

### Example 1 – Access a timestamp field from the payload 

Use `EntryTime` field from the payload as event timestamp 
 
```SQL  
SELECT  
      EntryTime,  
      LicensePlate,  
      State   
FROM input TIMESTAMP BY EntryTime  
```  
  
### Example 2 – Use UNIX time from the payload as event timestamp  

UNIX systems often use POSIX (or Epoch) time defined as the number of milliseconds that have elapsed since 00:00:00 Coordinated Universal Time (UTC), Thursday, 1 January 1970.  
  
 This example shows how to use numeric 'epochtime' field containing Epoch time as event timestamp. 
 
```SQL  
SELECT  
      System.Timestamp(),  
      LicensePlate,  
      State  
FROM input TIMESTAMP BY DATEADD(millisecond, epochtime, '1970-01-01T00:00:00Z')  
```  
  
### Example 3 – Heterogeneous timestamps    

Imagine processing heterogeneous streams of data containing two type of events 'A' and 'B'. Events 'A' have timestamp data in the field 'timestampA' and events 'B' have timestamp in the field 'timestampB'.  
  
 This example shows how to write TIMESTAMP BY to be able to work with both types of events/timestamps. 
  
```SQL  
SELECT  
      System.Timestamp(),  
      eventType,  
      eventValue,  
FROM input TIMESTAMP BY  
      (CASE eventType   
            WHEN 'A' THEN timestampA  
            WHEN 'B' THEN timestampB  
      ELSE NULL END) 
```  

### Example 4 – Handling multiple timelines in a partitioned query

Process data from different senders (toll stations) without applying time policies across different toll station IDs. The input data is partitioned based on TollId.

```SQL
SELECT
      TollId,
      COUNT(*) AS Count
FROM input
      TIMESTAMP BY EntryTime OVER TollId, PartitionId
      PARTITION BY PartitionId
GROUP BY TUMBLINGWINDOW(minute,3), TollId, PartitionId
 ```
 
## See Also  
 [System.Timestamp()](system-timestamp-stream-analytics.md)   
 [Time Skew Policies](time-skew-policies-azure-stream-analytics.md)   
 [Understand time handling in Azure Stream Analytics](/azure/stream-analytics/stream-analytics-time-handling)   
 [Unix Time](https://en.wikipedia.org/wiki/Unix_time)  
