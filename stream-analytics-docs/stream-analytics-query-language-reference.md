---
title: "Stream Analytics Query Language Reference"
description: "Azure Stream Analytics offers a SQL-like query language for performing transformations and computations over streams of events."
applies_to: 
  - "Azure"


ms.service: stream-analytics
ms.topic: reference
ms.date: 03/6/2020
---
# Stream Analytics Query Language Reference
  Azure Stream Analytics offers a SQL query language for performing transformations and computations over streams of events.  
  
## Stream Analytics Query Language, a subset of T-SQL syntax  
 This document describes the syntax, usage and best practices for the Stream Analytics query language. All the examples used in this document rely on a toll booth scenario as described below.  
  
 Stream Analytics query language is a subset of standard T-SQL syntax for doing Streaming computations.  
  
### The toll booth scenario  
 A tolling station is a common phenomenon – we encounter them in many expressways, bridges, and tunnels across the world. Each toll station has multiple toll booths, which may be manual – meaning that you stop to pay the toll to an attendant, or automated – where a sensor placed on top of the booth scans an RFID card affixed to the windshield of your vehicle as you pass the toll booth. It is easy to visualize the passage of vehicles through these toll stations as an event stream over which interesting operations can be performed.  
  
### Arrival Time Vs Application Time  
 In any temporal system like Azure Stream Analytics, it’s essential to understand the progress of time. Every event that flows through the system comes with a timestamp that can be accessed via [System.Timestamp()](system-timestamp-stream-analytics.md). In other words every event in our system depicts a point in time. This timestamp can either be an application time which the user can specify in the query or the system can assign based on arrival time. The arrival time has different meanings based on the input sources.  For the events from Azure Service Bus Event Hub, the arrival time is the timestamp given by the Event Hub; for Blob storage, it is the blob’s last modified time. The timestamp is the point in time that is relevant for capturing or analyzing data. If the user wants to use an application time, they can do so using the [TIMESTAMP BY](timestamp-by-azure-stream-analytics.md) keyword. In the above scenario, it is the entry of the vehicle to the toll booth. It is critical to identify the “timestamp” in the incoming stream of data, one should ensure that the time captured also confirms the occurrence of an event. For example, if one is monitoring cash counters and wants to count the number of customers billed, then ideally the event timestamp should be “payment successful” rather than “bill generated” time.  
  
### TIMESTAMP BY  
 In Azure Stream Analytics, all events have a well-defined timestamp. If the user wants to use application time, they can use the TIMESTAMP BY keyword to specify the column in the payload which should be used to timestamp every incoming event to perform any temporal computation like Windowing, Joins etc.  We recommend using TIMESTAMP BY over arrival time as a best practice.  TIMESTAMP BY can be used on any column of type datetime and all ISO 8601 formats are supported. System.Timestamp() can only be used in [Select](select-azure-stream-analytics.md).  
  
 The following is a TIMESTAMP BY example which uses the EntryTime column as the application time for events:  
  
```SQL  
  
SELECT TollId, EntryTime AS VehicleEntryTime, LicensePlate, State, Make, Model, VehicleType, VehicleWeight, Toll, Tag   
FROM TollTagEntry TIMESTAMP BY EntryTime  
  
```  
  
### Field Name Case Sensitivity  
 Field names for a job that is created by using compatibility level 1.0 are changed to lower case(case insensitive) when processed by the Azure Stream Analytics engine. For input formats that support case sensitive schema, for example JSON, you may construct events that have duplicate fields when field names are compared in a case insensitivity manner. Such events are considered invalid events, and are dropped during processing.  

  Case-sensitivity is persisted for field names when the Stream Analytics job is created by using compatibility level 1.1 or greater. For more information, refer to the [configure compatibility level](/azure/stream-analytics/stream-analytics-compatibility-level) topic.

 
## In this section  
 Refer to the following topics for guidance on using the Stream Analytics query language.  
  
-   [Built-in Functions &#40;Azure Stream Analytics&#41;](built-in-functions-azure-stream-analytics.md)  
  
-   [Data Types &#40;Azure Stream Analytics&#41;](data-types-azure-stream-analytics.md)  
  
-   [Query Language Elements &#40;Azure Stream Analytics&#41;](query-language-elements-azure-stream-analytics.md)  
  
-   [Time Management &#40;Azure Stream Analytics&#41;](time-management-azure-stream-analytics.md)  
  
-   [Windowing &#40;Azure Stream Analytics&#41;](windowing-azure-stream-analytics.md)  
  
## See Also  
  
-   [Stream Analytics REST API](https://msdn.microsoft.com/library/71a66e31-dfa5-48a7-8771-192f1490c205)  
  
  
