---
title: "Time Skew Policies (Azure Stream Analytics)"
description: "Describes how to handle temporal nature and timing of arrival of events in Azure Stream Analytics."
applies_to: 
  - "Azure"


ms.service: stream-analytics
ms.topic: reference
ms.date: 07/06/2020
---
# Time Skew Policies (Azure Stream Analytics)
  In Stream Analytics, all data stream events have a [timestamp](system-timestamp-stream-analytics.md) associated with them. Users can use the [TIMESTAMP BY](timestamp-by-azure-stream-analytics.md) keyword to choose between one of these two different times:
- **Application time**, that is to say the time the events are produced (as marked by the application/device generating the events). When using application time, you can either process all events using a global timeline, or analyse each device/partition using its own timeline using [substreams](/azure/stream-analytics/stream-analytics-time-handling#handle-time-variation-with-substreams);
- **Arrival time**, the time the event reached the cloud (e.g. arrival time in IoT Hub or Event Hub).
  
In addition to the choice of timestamp, users may need to define Late Arrival and Out of Order policy due to the following issues:
- **Producers of the events have clock skews**. This is common when producers are from different machines, so they have different clocks.
- **Due to network latency**, events originate from the same clock may arrive at Event Hub or IoT Hub in a different order from when they were originated
- **Clock skews between partitions**.  When using non-partitioned queries, events from all partitions are merged by the timestamp of user's choice. Clock skews between the partitions can result in delay of processing, because the merger needs to wait for the slowest partition.

Input streams that are not in order can be either: 
- Sorted (and therefore **delayed**).
- Adjusted by the system, according to the user-specified policy.

Stream Analytics tolerates late and out of order events when processing by application time.


  
## **Out of Order Policy**  
Having events ordered by time is very important in streaming analytics. However due to the 3 issues mentioned above, it is often the case that they are received out-of-order, which may affect the results of our queries.
The Out of Order Policy allows to **reorder events** by timestamp when they arrive within the defined tolerance window. 
Events that arrive later than tolerance are **either dropped or adjusted**, depending of the setting you choose.
- Adjusted: Adjusted to appear to have arrived at the latest acceptable time. 
- Dropped: Discarded.

This setting can be adjusted in the Azure portal (in the "Event Ordering" tab of a job). For more information, refer to [the event order considerations page](/azure/stream-analytics/stream-analytics-out-of-order-and-late-events).

When setting an out of order policy greater than 0, Stream Analytics will buffer events up to that window and reorder them using the user defined timestamp before applying the temporal transformation. Generally starting with a 3 second window first is a good best practice and then tune the value to reduce the number of events getting time adjusted. Note that because of the buffering, the side effect is the output is delayed by the same amount of time.
As a result, you will need to tune the value to reduce the number of out of order events and keep the latency low.


  
## **Late Arrival Tolerance**  
The late arrival tolerance window is used to account for delay in events reaching the input source because of various reasons outlined above.
Briefly, late arrival window is the maximum delay between event generation and receiving of the event at input source. Adjustment based on Late arrival tolerance is done first and out of order is done next. The **System.Timestamp()** column will have the final timestamp assigned to the event.

This setting is applicable only when processing by Application time, otherwise it is ignored. It can also be set in the Azure portal (in the "Event Ordering" tab of a job). For more information, refer to [the event order considerations page](/azure/stream-analytics/stream-analytics-out-of-order-and-late-events).

When an event is late, it's timestamp is adjusted to the current enqueue time at the input source minus the late arrival tolerance window (or dropped, depending on the action chosen).
When multiple partitions from the same input stream or multiple input streams are combined together, late arrival tolerance is the maximum amount of time every partition waits for new data. 


### **Late Arrival tolerance and Sparse events**  
Late Arrival policy allows Stream Analytics to move time forward and generate output in a timelier fashion in the absence of input events. This is very useful when input events are sparse (or not received at all in some of the Event Hub partitions).

For example, input events are generated once every minute for a *select** query. Without using this policy, Stream Analytics cannot generate output results until events arrive at all Event Hub partitions (to move the time forward). This may mean 16 minutes if the Event Hub has 16 partitions, and that each event is delivered to a different partition. With the default 5 second policy, the clock is moved forward 5 seconds after the first event, so the output event is generated 5 seconds after the first event.

  
## See Also  
 [Time Management &#40;Azure Stream Analytics&#41;](time-management-azure-stream-analytics.md)   
 [System.Timestamp()  &#40;Stream Analytics&#41;](system-timestamp-stream-analytics.md)   
 [TIMESTAMP BY &#40;Azure Stream Analytics&#41;](timestamp-by-azure-stream-analytics.md)  
 [Event Order Consideration](/azure/stream-analytics/stream-analytics-out-of-order-and-late-events)
  
  
