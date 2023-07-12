---
title: Supported metrics - Microsoft.Synapse/workspaces
description: Reference for Microsoft.Synapse/workspaces metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Synapse/workspaces  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Synapse/workspaces resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Data processed (bytes)<p><p>Amount of data processed by queries |`BuiltinSqlPoolDataProcessedBytes` |Bytes |Total |No Dimensions |No|
|Login attempts<p><p>Count of login attempts that succeded or failed |`BuiltinSqlPoolLoginAttempts` |Count |Total |Result |No|
|Requests ended<p><p>Count of Requests that succeeded, failed, or were cancelled |`BuiltinSqlPoolRequestsEnded` |Count |Total |Result |No|
|Activity runs ended<p><p>Count of integration activities that succeeded, failed, or were cancelled |`IntegrationActivityRunsEnded` |Count |Total |Result, FailureType, Activity, ActivityType, Pipeline |No|
|Link connection events<p><p>Number of Synapse Link connection events including start, stop and failure. |`IntegrationLinkConnectionEvents` |Count |Total |EventType, LinkConnectionName |No|
|Link processed rows<p><p>Changed row count processed by Synapse Link. |`IntegrationLinkProcessedChangedRows` |Count |Total |TableName, LinkConnectionName |No|
|Link processed data volume (bytes)<p><p>Data volume in bytes processed by Synapse Link. |`IntegrationLinkProcessedDataVolume` |Bytes |Total |TableName, LinkTableStatus, LinkConnectionName |No|
|Link latency in seconds<p><p>Synapse Link data processing latency in seconds. |`IntegrationLinkProcessingLatencyInSeconds` |Count |Maximum |LinkConnectionName |No|
|Link table events<p><p>Number of Synapse Link table events including snapshot, removal and failure. |`IntegrationLinkTableEvents` |Count |Total |TableName, EventType, LinkConnectionName |No|
|Pipeline runs ended<p><p>Count of integration pipeline runs that succeeded, failed, or were cancelled |`IntegrationPipelineRunsEnded` |Count |Total |Result, FailureType, Pipeline |No|
|Trigger Runs ended<p><p>Count of integration triggers that succeeded, failed, or were cancelled |`IntegrationTriggerRunsEnded` |Count |Total |Result, FailureType, Trigger |No|
|Backlogged input events (preview)<p><p>This is a preview metric available in East US, West Europe. Number of input events sources backlogged. |`SQLStreamingBackloggedInputEventSources` |Count |Total |SQLPoolName, SQLDatabaseName, JobName, LogicalName, PartitionId, ProcessorInstance |No|
|Data conversion errors (preview)<p><p>This is a preview metric available in East US, West Europe. Number of output events that could not be converted to the expected output schema. Error policy can be changed to 'Drop' to drop events that encounter this scenario. |`SQLStreamingConversionErrors` |Count |Total |SQLPoolName, SQLDatabaseName, JobName, LogicalName, PartitionId, ProcessorInstance |No|
|Input deserialization errors (preview)<p><p>This is a preview metric available in East US, West Europe. Number of input events that could not be deserialized. |`SQLStreamingDeserializationError` |Count |Total |SQLPoolName, SQLDatabaseName, JobName, LogicalName, PartitionId, ProcessorInstance |No|
|Early input events (preview)<p><p>This is a preview metric available in East US, West Europe. Number of input events which application time is considered early compared to arrival time, according to early arrival policy. |`SQLStreamingEarlyInputEvents` |Count |Total |SQLPoolName, SQLDatabaseName, JobName, LogicalName, PartitionId, ProcessorInstance |No|
|Input event bytes (preview)<p><p>This is a preview metric available in East US, West Europe. Amount of data received by the streaming job, in bytes. This can be used to validate that events are being sent to the input source. |`SQLStreamingInputEventBytes` |Count |Total |SQLPoolName, SQLDatabaseName, JobName, LogicalName, PartitionId, ProcessorInstance |No|
|Input events (preview)<p><p>This is a preview metric available in East US, West Europe. Number of input events. |`SQLStreamingInputEvents` |Count |Total |SQLPoolName, SQLDatabaseName, JobName, LogicalName, PartitionId, ProcessorInstance |No|
|Input sources received (preview)<p><p>This is a preview metric available in East US, West Europe. Number of input events sources per second. |`SQLStreamingInputEventsSourcesPerSecond` |Count |Total |SQLPoolName, SQLDatabaseName, JobName, LogicalName, PartitionId, ProcessorInstance |No|
|Late input events (preview)<p><p>This is a preview metric available in East US, West Europe. Number of input events which application time is considered late compared to arrival time, according to late arrival policy. |`SQLStreamingLateInputEvents` |Count |Total |SQLPoolName, SQLDatabaseName, JobName, LogicalName, PartitionId, ProcessorInstance |No|
|Out of order events (preview)<p><p>This is a preview metric available in East US, West Europe. Number of Event Hub Events (serialized messages) received by the Event Hub Input Adapter, received out of order that were either dropped or given an adjusted timestamp, based on the Event Ordering Policy. |`SQLStreamingOutOfOrderEvents` |Count |Total |SQLPoolName, SQLDatabaseName, JobName, LogicalName, PartitionId, ProcessorInstance |No|
|Output events (preview)<p><p>This is a preview metric available in East US, West Europe. Number of output events. |`SQLStreamingOutputEvents` |Count |Total |SQLPoolName, SQLDatabaseName, JobName, LogicalName, PartitionId, ProcessorInstance |No|
|Watermark delay (preview)<p><p>This is a preview metric available in East US, West Europe. Output watermark delay in seconds. |`SQLStreamingOutputWatermarkDelaySeconds` |Count |Maximum |SQLPoolName, SQLDatabaseName, JobName, LogicalName, PartitionId, ProcessorInstance |No|
|Resource % utilization (preview)<p><p>This is a preview metric available in East US, West Europe. Resource utilization expressed as a percentage. High utilization indicates that the job is using close to the maximum allocated resources. |`SQLStreamingResourceUtilization` |Percent |Maximum |SQLPoolName, SQLDatabaseName, JobName, LogicalName, PartitionId, ProcessorInstance |No|
|Runtime errors (preview)<p><p>This is a preview metric available in East US, West Europe. Total number of errors related to query processing (excluding errors found while ingesting events or outputting results). |`SQLStreamingRuntimeErrors` |Count |Total |SQLPoolName, SQLDatabaseName, JobName, LogicalName, PartitionId, ProcessorInstance |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->