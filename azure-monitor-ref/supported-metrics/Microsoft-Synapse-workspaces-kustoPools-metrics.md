---
title: Supported metrics - Microsoft.Synapse/workspaces/kustoPools
description: Reference for Microsoft.Synapse/workspaces/kustoPools metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Synapse/workspaces/kustoPools  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Synapse/workspaces/kustoPools resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Batch Blob Count<p><p>Number of data sources in an aggregated batch for ingestion. |`BatchBlobCount` |Count |Average |Database |Yes|
|Batch Duration<p><p>The duration of the aggregation phase in the ingestion flow. |`BatchDuration` |Seconds |Average |Database |Yes|
|Batches Processed<p><p>Number of batches aggregated for ingestion. Batching Type: whether the batch reached batching time, data size or number of files limit set by batching policy |`BatchesProcessed` |Count |Total |Database, SealReason |Yes|
|Batch Size<p><p>Uncompressed expected data size in an aggregated batch for ingestion. |`BatchSize` |Bytes |Average |Database |Yes|
|Blobs Dropped<p><p>Number of blobs permanently rejected by a component. |`BlobsDropped` |Count |Total |Database, ComponentType, ComponentName |Yes|
|Blobs Processed<p><p>Number of blobs processed by a component. |`BlobsProcessed` |Count |Total |Database, ComponentType, ComponentName |Yes|
|Blobs Received<p><p>Number of blobs received from input stream by a component. |`BlobsReceived` |Count |Total |Database, ComponentType, ComponentName |Yes|
|Cache utilization (deprecated)<p><p>Utilization level in the cluster scope. The metric is deprecated and presented for backward compatibility only, you should use the 'Cache utilization factor' metric instead. |`CacheUtilization` |Percent |Average |No Dimensions |Yes|
|Cache utilization factor<p><p>Percentage of utilized disk space dedicated for hot cache in the cluster. 100% means that the disk space assigned to hot data is optimally utilized. No action is needed in terms of the cache size. More than 100% means that the cluster's disk space is not large enough to accommodate the hot data, as defined by your caching policies. To ensure that sufficient space is available for all the hot data, the amount of hot data needs to be reduced or the cluster needs to be scaled out. Enabling auto scale is recommended. |`CacheUtilizationFactor` |Percent |Average |No Dimensions |Yes|
|Continuous Export Max Lateness<p><p>The lateness (in minutes) reported by the continuous export jobs in the cluster |`ContinuousExportMaxLatenessMinutes` |Count |Maximum |No Dimensions |Yes|
|Continuous export - num of exported records<p><p>Number of records exported, fired for every storage artifact written during the export operation |`ContinuousExportNumOfRecordsExported` |Count |Total |ContinuousExportName, Database |Yes|
|Continuous Export Pending Count<p><p>The number of pending continuous export jobs ready for execution |`ContinuousExportPendingCount` |Count |Maximum |No Dimensions |Yes|
|Continuous Export Result<p><p>Indicates whether Continuous Export succeeded or failed |`ContinuousExportResult` |Count |Count |ContinuousExportName, Result, Database |Yes|
|CPU<p><p>CPU utilization level |`CPU` |Percent |Average |No Dimensions |Yes|
|Discovery Latency<p><p>Reported by data connections (if exist). Time in seconds from when a message is enqueued or event is created until it is discovered by data connection. This time is not included in the Azure Data Explorer total ingestion duration. |`DiscoveryLatency` |Seconds |Average |ComponentType, ComponentName |Yes|
|Events Dropped<p><p>Number of events dropped permanently by data connection. An Ingestion result metric with a failure reason will be sent. |`EventsDropped` |Count |Total |ComponentType, ComponentName |Yes|
|Events Processed<p><p>Number of events processed by the cluster |`EventsProcessed` |Count |Total |ComponentType, ComponentName |Yes|
|Events Processed (for Event/IoT Hubs)<p><p>Number of events processed by the cluster when ingesting from Event/IoT Hub |`EventsProcessedForEventHubs` |Count |Total |EventStatus |Yes|
|Events Received<p><p>Number of events received by data connection. |`EventsReceived` |Count |Total |ComponentType, ComponentName |Yes|
|Export Utilization<p><p>Export utilization |`ExportUtilization` |Percent |Maximum |No Dimensions |Yes|
|FollowerLatency<p><p>The follower databases synchronize changes in the leader databases. Because of the synchronization, there's a data lag of a few seconds to a few minutes in data availability.This metric measures the length of the time lag. The time lag depends on the overall size of the leader database metadata.This is a cluster level metrics: the followers catch metadata of all databases that are followed. This metric represents the latency of the process. |`FollowerLatency` |MilliSeconds |Average |State, RoleInstance |Yes|
|Ingestion Latency<p><p>Latency of data ingested, from the time the data was received in the cluster until it's ready for query. The ingestion latency period depends on the ingestion scenario. |`IngestionLatencyInSeconds` |Seconds |Average |No Dimensions |Yes|
|Ingestion result<p><p>Total number of sources that either failed or succeeded to be ingested. Splitting the metric by status, you can get detailed information about the status of the ingestion operations. |`IngestionResult` |Count |Total |IngestionResultDetails, FailureKind |Yes|
|Ingestion utilization<p><p>Ratio of used ingestion slots in the cluster |`IngestionUtilization` |Percent |Average |No Dimensions |Yes|
|Ingestion Volume<p><p>Overall volume of ingested data to the cluster |`IngestionVolumeInMB` |Bytes |Total |Database |Yes|
|Instance Count<p><p>Total instance count |`InstanceCount` |Count |Average |No Dimensions |Yes|
|Keep alive<p><p>Sanity check indicates the cluster responds to queries |`KeepAlive` |Count |Average |No Dimensions |Yes|
|Materialized View Age<p><p>The materialized view age in minutes |`MaterializedViewAgeMinutes` |Count |Average |Database, MaterializedViewName |Yes|
|Materialized View Age<p><p>The materialized view age in seconds |`MaterializedViewAgeSeconds` |Seconds |Average |Database, MaterializedViewName |Yes|
|Materialized View Data Loss<p><p>Indicates potential data loss in materialized view |`MaterializedViewDataLoss` |Count |Maximum |Database, MaterializedViewName, Kind |Yes|
|Materialized View Extents Rebuild<p><p>Number of extents rebuild |`MaterializedViewExtentsRebuild` |Count |Average |Database, MaterializedViewName |Yes|
|Materialized View Health<p><p>The health of the materialized view (1 for healthy, 0 for non-healthy) |`MaterializedViewHealth` |Count |Average |Database, MaterializedViewName |Yes|
|Materialized View Records In Delta<p><p>The number of records in the non-materialized part of the view |`MaterializedViewRecordsInDelta` |Count |Average |Database, MaterializedViewName |Yes|
|Materialized View Result<p><p>The result of the materialization process |`MaterializedViewResult` |Count |Average |Database, MaterializedViewName, Result |Yes|
|Query duration<p><p>Queries duration in seconds |`QueryDuration` |MilliSeconds |Average |QueryStatus |Yes|
|Query Result<p><p>Total number of queries. |`QueryResult` |Count |Count |QueryStatus |No|
|Queue Length<p><p>Number of pending messages in a component's queue. |`QueueLength` |Count |Average |ComponentType |Yes|
|Queue Oldest Message<p><p>Time in seconds from when the oldest message in queue was inserted. |`QueueOldestMessage` |Count |Average |ComponentType |Yes|
|Received Data Size Bytes<p><p>Size of data received by data connection. This is the size of the data stream, or of raw data size if provided. |`ReceivedDataSizeBytes` |Bytes |Average |ComponentType, ComponentName |Yes|
|Stage Latency<p><p>Cumulative time from when a message is discovered until it is received by the reporting component for processing (discovery time is set when message is enqueued for ingestion queue, or when discovered by data connection). |`StageLatency` |Seconds |Average |Database, ComponentType |Yes|
|Streaming Ingest Data Rate<p><p>Streaming ingest data rate |`StreamingIngestDataRate` |Bytes |Average |No Dimensions |Yes|
|Streaming Ingest Duration<p><p>Streaming ingest duration in milliseconds |`StreamingIngestDuration` |MilliSeconds |Average |No Dimensions |Yes|
|Streaming Ingest Result<p><p>Streaming ingest result |`StreamingIngestResults` |Count |Count |Result |Yes|
|Total number of concurrent queries<p><p>Total number of concurrent queries |`TotalNumberOfConcurrentQueries` |Count |Maximum |No Dimensions |Yes|
|Total number of extents<p><p>Total number of data extents |`TotalNumberOfExtents` |Count |Average |No Dimensions |Yes|
|Total number of throttled commands<p><p>Total number of throttled commands |`TotalNumberOfThrottledCommands` |Count |Total |CommandType |Yes|
|Total number of throttled queries<p><p>Total number of throttled queries |`TotalNumberOfThrottledQueries` |Count |Maximum |No Dimensions |Yes|
|Weak consistency latency<p><p>The max latency between the previous metadata sync and the next one (in DB/node scope) |`WeakConsistencyLatency` |Seconds |Average |Database, RoleInstance |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->