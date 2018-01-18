---
title: "Time Skew Policies (Azure Stream Analytics) | Microsoft Docs"
description: "Describes how to handle temporal nature and timing of arrival of events in Azure Stream Analytics."
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: 3821da4a-53e6-4f15-97f9-b6e3bde759b9
caps.latest.revision: 10
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---
# Time Skew Policies (Azure Stream Analytics)
  In Stream Analytics, all data stream events have a timestamp associated with them. As all events are temporal in nature and timing of arrival of the event is how the timestamp is assigned, considerations exists for both the tolerance of out of order events and the late arrival of events to the Stream Analytics job. Contributors to Late Arrival and Out of Order event vary but generally are one or more of the following:  
  
-   Producers of the events have clock skews. This is common when producers are from different machines, so they have different clocks.  
  
-   Network delay from the producers sending the events to Event Hub.  
  
-   Clock skews between Event Hub partitions. This is also a factor because we first sort events from all Event Hub partitions by event enqueue time, and then examine the disordness.  
  
## **Out of Order Policy**  
 Because Stream Analytics applies temporal transformation when processing the incoming events (e.g. windowed aggregates, and temporal joins), the incoming events are sorted by timestamp order. The user has the choice of which timestamp to use by using the **timestamp by** clause in the query (e.g. `select * from input timestamp by time`, where time is a field in the event payload).  
When "timestamp by" is not present, we use Event Hub's event enqueue time by default. Because Event Hub guarantees monotonicity of the timestamp on each partition of the Event Hub and we merge events from all partitions by timestamp order, there will be no out of order events.  
  
 When configuring an event ordering policy (found in the configuration tab of a job), using 0 seconds as the out of order tolerance window means you assert all events are in order all the time. Given the 3 sources of disorderness, this is unlikely to be true all the time. Specify a non-zero out of order tolerance window size to allow Stream Analytics to correct the disorderness. Stream Analytics will buffer events up to that window and reorder them using the user defined timestamp before applying the temporal transformation. Generally starting with a 3 second window first is a good best practice and then tune the value to reduce the number of events getting time adjusted. Note that because of the buffering, the side effect is the output is delayed by the same amount of time.  
  
 As a result, you will need to tune the value to reduce the number of out of order events and keep the latency low.  
  
## **Late Arrival Policy**  
 The late arrival tolerance window is used to account for delay in events reaching the input source because of various reasons outlined above.  
  
 However, the lateness is between the timestamp in the **timestamp by** field and the enqueue time of the event at input source (e.g. Event Hub). This means when **timestamp by** is not used, this tolerance window is meaningless and ignored. When an event is late, it’s timestamp is adjusted to the current enqueue time at the input source minus the late arrival tolerance window (or dropped, depending on the action chosen).  
  
 This policy allows Stream Analytics to move time forward and generate output in a timelier fashion in the absence of input events. This is very useful when input events are sparse (or not received at all in some of the Event Hub partitions).  
  
 For example, input events are generated once every minute for a `select *` query. Without using this policy, Stream Analytics cannot generate output results until events arrive at all Event Hub partitions (to move the time forward). This may mean 16 minutes if the Event Hub has 16 partitions, and that each event is delivered to a different partition. With the default 5 second policy, the clock is moved forward 5 seconds after the first event, so the output event is generated 5 seconds after the first event.  
  
## See Also  
 [Time Management &#40;Azure Stream Analytics&#41;](time-management-azure-stream-analytics.md)   
 [System.Timestamp  &#40;Stream Analytics&#41;](system-timestamp-stream-analytics.md)   
 [TIMESTAMP BY &#40;Azure Stream Analytics&#41;](timestamp-by-azure-stream-analytics.md)  
  
  