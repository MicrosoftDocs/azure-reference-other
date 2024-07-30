---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Synapse/workspaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Built-in SQL Pool|**Data processed (bytes)**<br><br>Amount of data processed by queries |`BuiltinSqlPoolDataProcessedBytes` |Bytes |Total |\<none\>|PT1M |No|
|Built-in SQL Pool|**Login attempts**<br><br>Count of login attempts that succeded or failed |`BuiltinSqlPoolLoginAttempts` |Count |Average, Minimum, Maximum, Total |`Result`|PT1M |No|
|Built-in SQL Pool|**Requests ended**<br><br>Count of Requests that succeeded, failed, or were cancelled |`BuiltinSqlPoolRequestsEnded` |Count |Average, Minimum, Maximum, Total |`Result`|PT1M |No|
|Integration|**Activity runs ended**<br><br>Count of integration activities that succeeded, failed, or were cancelled |`IntegrationActivityRunsEnded` |Count |Count, Total |`Result`, `FailureType`, `Activity`, `ActivityType`, `Pipeline`|PT1M, PT1H |No|
|Integration|**Link connection events**<br><br>Number of Synapse Link connection events including start, stop and failure. |`IntegrationLinkConnectionEvents` |Count |Total |`EventType`, `LinkConnectionName`|PT1M |No|
|Integration|**Link processed rows**<br><br>Changed row count processed by Synapse Link. |`IntegrationLinkProcessedChangedRows` |Count |Total |`TableName`, `LinkConnectionName`|PT1M |No|
|Integration|**Link processed data volume (bytes)**<br><br>Data volume in bytes processed by Synapse Link. |`IntegrationLinkProcessedDataVolume` |Bytes |Total |`TableName`, `LinkTableStatus`, `LinkConnectionName`|PT1M |No|
|Integration|**Link latency in seconds**<br><br>Synapse Link data processing latency in seconds. |`IntegrationLinkProcessingLatencyInSeconds` |Count |Maximum, Minimum, Average |`LinkConnectionName`|PT1M |No|
|Integration|**Link table events**<br><br>Number of Synapse Link table events including snapshot, removal and failure. |`IntegrationLinkTableEvents` |Count |Total |`TableName`, `EventType`, `LinkConnectionName`|PT1M |No|
|Integration|**Pipeline runs ended**<br><br>Count of integration pipeline runs that succeeded, failed, or were cancelled |`IntegrationPipelineRunsEnded` |Count |Count, Total |`Result`, `FailureType`, `Pipeline`|PT1M, PT1H |No|
|Integration|**Trigger Runs ended**<br><br>Count of integration triggers that succeeded, failed, or were cancelled |`IntegrationTriggerRunsEnded` |Count |Count, Total |`Result`, `FailureType`, `Trigger`|PT1M, PT1H |No|
|Streaming job|**Backlogged input events (preview)**<br><br>This is a preview metric available in East US, West Europe. Number of input events sources backlogged. |`SQLStreamingBackloggedInputEventSources` |Count |Total |`SQLPoolName`, `SQLDatabaseName`, `JobName`, `LogicalName`, `PartitionId`, `ProcessorInstance`|PT1M |No|
|Streaming job|**Data conversion errors (preview)**<br><br>This is a preview metric available in East US, West Europe. Number of output events that could not be converted to the expected output schema. Error policy can be changed to 'Drop' to drop events that encounter this scenario. |`SQLStreamingConversionErrors` |Count |Total |`SQLPoolName`, `SQLDatabaseName`, `JobName`, `LogicalName`, `PartitionId`, `ProcessorInstance`|PT1M |No|
|Streaming job|**Input deserialization errors (preview)**<br><br>This is a preview metric available in East US, West Europe. Number of input events that could not be deserialized. |`SQLStreamingDeserializationError` |Count |Total |`SQLPoolName`, `SQLDatabaseName`, `JobName`, `LogicalName`, `PartitionId`, `ProcessorInstance`|PT1M |No|
|Streaming job|**Early input events (preview)**<br><br>This is a preview metric available in East US, West Europe. Number of input events which application time is considered early compared to arrival time, according to early arrival policy. |`SQLStreamingEarlyInputEvents` |Count |Total |`SQLPoolName`, `SQLDatabaseName`, `JobName`, `LogicalName`, `PartitionId`, `ProcessorInstance`|PT1M |No|
|Streaming job|**Input event bytes (preview)**<br><br>This is a preview metric available in East US, West Europe. Amount of data received by the streaming job, in bytes. This can be used to validate that events are being sent to the input source. |`SQLStreamingInputEventBytes` |Count |Total |`SQLPoolName`, `SQLDatabaseName`, `JobName`, `LogicalName`, `PartitionId`, `ProcessorInstance`|PT1M |No|
|Streaming job|**Input events (preview)**<br><br>This is a preview metric available in East US, West Europe. Number of input events. |`SQLStreamingInputEvents` |Count |Total |`SQLPoolName`, `SQLDatabaseName`, `JobName`, `LogicalName`, `PartitionId`, `ProcessorInstance`|PT1M |No|
|Streaming job|**Input sources received (preview)**<br><br>This is a preview metric available in East US, West Europe. Number of input events sources per second. |`SQLStreamingInputEventsSourcesPerSecond` |Count |Total |`SQLPoolName`, `SQLDatabaseName`, `JobName`, `LogicalName`, `PartitionId`, `ProcessorInstance`|PT1M |No|
|Streaming job|**Late input events (preview)**<br><br>This is a preview metric available in East US, West Europe. Number of input events which application time is considered late compared to arrival time, according to late arrival policy. |`SQLStreamingLateInputEvents` |Count |Total |`SQLPoolName`, `SQLDatabaseName`, `JobName`, `LogicalName`, `PartitionId`, `ProcessorInstance`|PT1M |No|
|Streaming job|**Out of order events (preview)**<br><br>This is a preview metric available in East US, West Europe. Number of Event Hub Events (serialized messages) received by the Event Hub Input Adapter, received out of order that were either dropped or given an adjusted timestamp, based on the Event Ordering Policy. |`SQLStreamingOutOfOrderEvents` |Count |Total |`SQLPoolName`, `SQLDatabaseName`, `JobName`, `LogicalName`, `PartitionId`, `ProcessorInstance`|PT1M |No|
|Streaming job|**Output events (preview)**<br><br>This is a preview metric available in East US, West Europe. Number of output events. |`SQLStreamingOutputEvents` |Count |Total |`SQLPoolName`, `SQLDatabaseName`, `JobName`, `LogicalName`, `PartitionId`, `ProcessorInstance`|PT1M |No|
|Streaming job|**Watermark delay (preview)**<br><br>This is a preview metric available in East US, West Europe. Output watermark delay in seconds. |`SQLStreamingOutputWatermarkDelaySeconds` |Count |Maximum, Minimum, Average |`SQLPoolName`, `SQLDatabaseName`, `JobName`, `LogicalName`, `PartitionId`, `ProcessorInstance`|PT1M |No|
|Streaming job|**Resource % utilization (preview)**<br><br>This is a preview metric available in East US, West Europe.<br><br> Resource utilization expressed as a percentage. High utilization indicates that the job is using close to the maximum allocated resources. |`SQLStreamingResourceUtilization` |Percent |Maximum, Minimum, Average |`SQLPoolName`, `SQLDatabaseName`, `JobName`, `LogicalName`, `PartitionId`, `ProcessorInstance`|PT1M |No|
|Streaming job|**Runtime errors (preview)**<br><br>This is a preview metric available in East US, West Europe. Total number of errors related to query processing (excluding errors found while ingesting events or outputting results). |`SQLStreamingRuntimeErrors` |Count |Total |`SQLPoolName`, `SQLDatabaseName`, `JobName`, `LogicalName`, `PartitionId`, `ProcessorInstance`|PT1M |No|