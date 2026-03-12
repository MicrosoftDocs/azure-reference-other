---
title: "Time Skew Policies"
description: "Describes how to handle temporal nature and timing of arrival of events in Azure Stream Analytics."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 03/04/2026
---
# Time Skew Policies
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

[!INCLUDE [stream-analytics-fabric-event-stream-query-language](./includes/stream-analytics-fabric-event-stream-query-language.md)]

All data stream events have a [timestamp](system-timestamp-stream-analytics.md) associated with them. Users can use the [TIMESTAMP BY](timestamp-by-azure-stream-analytics.md) keyword to choose between one of these two different times:
- **Application time**: The time the events are produced (as marked by the application/device generating the events). When using application time, you can either process all events using a global timeline, or analyze each device/partition using its own timeline using [substreams](/azure/stream-analytics/stream-analytics-time-handling#handle-time-variation-with-substreams);
- **Arrival time**: The time the event reached the cloud (for example, arrival time in IoT Hub or Event Hubs).
  
In addition to the choice of timestamp, users might need to define Late Arrival and Out of Order policy due to the following issues:
- **Producers of the events have clock skews**. This issue is common when producers are from different machines, so they have different clocks.
- **Due to network latency**, events originate from the same clock might arrive at Event Hubs or IoT Hub in a different order from when they were originated
- **Clock skews between partitions**. When you use nonpartitioned queries, events from all partitions are merged by the timestamp of user's choice. Clock skews between the partitions can result in delay of processing, because the merger needs to wait for the slowest partition.

Input streams that aren't in order are due to the following reasons:
- Sorted (and therefore **delayed**).
- Adjusted by the system, according to the user-specified policy.

Stream Analytics tolerates late and out of order events when processing by application time.


  
## **Out of Order Policy**  
Having events ordered by time is very important in streaming analytics. However due to the three issues mentioned earlier, it's often the case that they're received out-of-order, which might affect the results of our queries.
The Out of Order Policy allows to **reorder events** by timestamp when they arrive within the defined tolerance window. 
Events that arrive later than tolerance are **either dropped or adjusted**, depending of the setting you choose.
- Adjusted: Adjusted to appear to have arrived at the latest acceptable time. 
- Dropped: Discarded.

This setting can be adjusted in the Azure portal (in the "Event Ordering" tab of a job). For more information, see [the event order considerations page](/azure/stream-analytics/stream-analytics-out-of-order-and-late-events).

When setting an out of order policy greater than zero, Stream Analytics buffers events up to that window and reorder them using the user defined timestamp before applying the temporal transformation. Generally starting with a 3-second window first is a best practice and then tune the value to reduce the number of events getting time adjusted. Because of the buffering, the side effect is the output is delayed by the same amount of time.
As a result, you need to tune the value to reduce the number of out of order events and keep the latency low.


  
## **Late Arrival Tolerance**  
The late arrival tolerance window is used to account for delay in events reaching the input source because of various reasons outlined earlier.
Briefly, late arrival window is the maximum delay between event generation and receiving of the event at input source. Adjustment based on Late arrival tolerance is done first and out of order is done next. The **System.Timestamp()** column has the final timestamp assigned to the event.

This setting is applicable only when processing by Application time, otherwise it's ignored. It can also be set in the Azure portal (in the "Event Ordering" tab of a job). For more information, see [the event order considerations page](/azure/stream-analytics/stream-analytics-out-of-order-and-late-events).

When an event is late, its timestamp is adjusted to the current enqueue time at the input source minus the late arrival tolerance window (or dropped, depending on the action chosen).
When multiple partitions from the same input stream or multiple input streams are combined together, late arrival tolerance is the maximum amount of time every partition waits for new data. 


### **Late Arrival tolerance and Sparse events**  
Late Arrival policy allows Stream Analytics to move time forward and generate output in a timelier fashion in the absence of input events. This feature is useful when input events are sparse (or not received at all in some of the Event Hubs partitions).

For example, input events are generated once every minute for a *select** query. Without using this policy, Stream Analytics can't generate output results until events arrive at all Event Hubs partitions (to move the time forward). This behavior means 16 minutes if the Event Hubs has 16 partitions, and that each event is delivered to a different partition. With the default 5-second policy, the clock is moved forward 5 seconds after the first event, so the output event is generated 5 seconds after the first event.

  
## See Also  
 [Time Management](time-management-azure-stream-analytics.md)   
 [System.Timestamp()  &#40;Stream Analytics&#41;](system-timestamp-stream-analytics.md)   
 [TIMESTAMP BY](timestamp-by-azure-stream-analytics.md)  
 [Event Order Consideration](/azure/stream-analytics/stream-analytics-out-of-order-and-late-events)
  
  
