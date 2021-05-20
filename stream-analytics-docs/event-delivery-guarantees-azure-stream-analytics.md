---
title: "Event Delivery Guarantees (Azure Stream Analytics)"
description: "Describes the event delivery mechanisms supported in Azure Stream Analytics."
applies_to: 
  - "Azure"


ms.service: stream-analytics
ms.topic: reference
ms.date: 12/17/2018
---
# Event Delivery Guarantees (Azure Stream Analytics)
Azure Stream Analytics query language extends SQL syntax to enable complex computations over streams of events. With Stream Analytics there are some concepts related to Event Delivery worth discussing. They are:  
  
*   Exactly once processing 
*   Exactly once delivery  
*   Duplicate records  
  
## Exactly-once processing  
Exactly-once processing guarantee means that given a set of inputs, the system always returns the same results. This is very important for repeatability, and applies even in case of restart of the job, or aross multiple jobs running in parallel on the same input. Azure Stream Analytics guarantees exactly once processing. 

## Exactly-once delivery  
Exactly-once delivery guarantee means all outputs from exactly-once processing are delivered to the output sink exactly once, so there is no duplicate output. This requires transactional capabilities on the output adaptor to be achieved.

Azure Stream Analytics guarantes at-least-once delivery to output sinks, which guarantees that all results are outputted, but duplicate results may occur. However exactly-once delivery may be achieved with several outputs such as Cosmos DB or SQL.
  
### Duplicate records  
Due to at-least-once delivery guarantee, when a Stream Analytics job is running, duplicate records may occasionally be noticed in the output data. These duplicate records are expected because Azure Stream Analytics output adapters don’t write the output events transactionally. This 'duplicate record' scenario can result if one of the following conditions occur;  
  
- The Azure instance is upgraded while the job is running  
- The Stream Analytics job is upgraded or an issue occurs with connectivity or reliability to the job output   
- The Azure instance running the job has an outage
- Stream Analytics job is started with the [*when last stopped*](/azure/stream-analytics/start-job#start-options) option
  
The downstream consumer of the output events need to dedupe the events using logical identity of the events. For example, if you are aggregating events by groups in a tumbling window, the logical identity of the event is the groups and the tumbling window’s end time. If you are running a pass through query, you may need to carry a unique id on the event in order to dedupe.  

### Output supporting exact-once delivery with Azure Stream Analytics
#### Cosmos DB
Using Cosmos DB, Azure Stream Analytics guarantees exactly-once delivery. Since Azure Stream Analytics uses upsert, no action is needed by the user. See more information on [Azure Stream Analytics output to CosmosDB](/azure/stream-analytics/stream-analytics-documentdb-output).

#### SQL
When using SQL output, users can achieve exactly-once delivery if the following requirements are met:
- all output streaming events have a natural key, i.e. are uniquely identifiable either by a field or a combination of fields.
- the output SQL table has a unique constraint (or primary key) created using the natural key of the output events.

This is sufficient to avoid duplicates because the SQL output honors any constraints placed on the table by skipping any events that cause a unique constraint violation.

#### Azure Table

All entities in an Azure Storage Table are uniquely identified by the concatenation of the `RowKey` and `PartitionKey` fields. Azure Stream Analytics upserts entities, so the value of a table entity will be the latest output event with the corresponding `RowKey`/`PartitionKey` combination. Therefore, to achieve exactly-once delivery, ensure that each output event has a unique `RowKey`/`PartitionKey` combination. If this is done, duplicate events will overwrite earlier versions. (The system-defined `Timestamp` field, which is the last modified time for the entity, will still change in this case.)

## See Also  
 [Time Management](time-management-azure-stream-analytics.md)  
