---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Synapse/workspaces/kustoPools, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Batch Blob Count**<p><p>Number of data sources in an aggregated batch for ingestion. |`BatchBlobCount` |Count |Average, Maximum, Minimum |`Database`|PT1M |Yes|
|**Batch Duration**<p><p>The duration of the aggregation phase in the ingestion flow. |`BatchDuration` |Seconds |Average, Maximum, Minimum |`Database`|PT1M |Yes|
|**Batches Processed**<p><p>Number of batches aggregated for ingestion. Batching Type: whether the batch reached batching time, data size or number of files limit set by batching policy |`BatchesProcessed` |Count |Total, Average, Maximum, Minimum |`Database`, `SealReason`|PT1M |Yes|
|**Batch Size**<p><p>Uncompressed expected data size in an aggregated batch for ingestion. |`BatchSize` |Bytes |Average, Maximum, Minimum |`Database`|PT1M |Yes|
|**Blobs Dropped**<p><p>Number of blobs permanently rejected by a component. |`BlobsDropped` |Count |Total, Average, Minimum, Maximum |`Database`, `ComponentType`, `ComponentName`|PT1M |Yes|
|**Blobs Processed**<p><p>Number of blobs processed by a component. |`BlobsProcessed` |Count |Total, Average, Minimum, Maximum |`Database`, `ComponentType`, `ComponentName`|PT1M |Yes|
|**Blobs Received**<p><p>Number of blobs received from input stream by a component. |`BlobsReceived` |Count |Total, Average, Minimum, Maximum |`Database`, `ComponentType`, `ComponentName`|PT1M |Yes|
|**Cache utilization (deprecated)**<p><p>Utilization level in the cluster scope. The metric is deprecated and presented for backward compatibility only, you should use the 'Cache utilization factor' metric instead. |`CacheUtilization` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Cache utilization factor**<p><p>Percentage of utilized disk space dedicated for hot cache in the cluster. 100% means that the disk space assigned to hot data is optimally utilized. No action is needed in terms of the cache size. More than 100% means that the cluster's disk space is not large enough to accommodate the hot data, as defined by your caching policies. To ensure that sufficient space is available for all the hot data, the amount of hot data needs to be reduced or the cluster needs to be scaled out. Enabling auto scale is recommended. |`CacheUtilizationFactor` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Continuous Export Max Lateness**<p><p>The lateness (in minutes) reported by the continuous export jobs in the cluster |`ContinuousExportMaxLatenessMinutes` |Count |Maximum |\<none\>|PT1M |Yes|
|**Continuous export - num of exported records**<p><p>Number of records exported, fired for every storage artifact written during the export operation |`ContinuousExportNumOfRecordsExported` |Count |Total |`ContinuousExportName`, `Database`|PT1M |Yes|
|**Continuous Export Pending Count**<p><p>The number of pending continuous export jobs ready for execution |`ContinuousExportPendingCount` |Count |Maximum |\<none\>|PT1M |Yes|
|**Continuous Export Result**<p><p>Indicates whether Continuous Export succeeded or failed |`ContinuousExportResult` |Count |Count |`ContinuousExportName`, `Result`, `Database`|PT1M |Yes|
|**CPU**<p><p>CPU utilization level |`CPU` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Discovery Latency**<p><p>Reported by data connections (if exist). Time in seconds from when a message is enqueued or event is created until it is discovered by data connection. This time is not included in the Azure Data Explorer total ingestion duration. |`DiscoveryLatency` |Seconds |Average |`ComponentType`, `ComponentName`|PT1M |Yes|
|**Events Dropped**<p><p>Number of events dropped permanently by data connection. An Ingestion result metric with a failure reason will be sent. |`EventsDropped` |Count |Total, Average, Minimum, Maximum |`ComponentType`, `ComponentName`|PT1M |Yes|
|**Events Processed**<p><p>Number of events processed by the cluster |`EventsProcessed` |Count |Total, Average, Minimum, Maximum |`ComponentType`, `ComponentName`|PT1M |Yes|
|**Events Processed (for Event/IoT Hubs)**<p><p>Number of events processed by the cluster when ingesting from Event/IoT Hub |`EventsProcessedForEventHubs` |Count |Maximum, Minimum, Total |`EventStatus`|PT1M |Yes|
|**Events Received**<p><p>Number of events received by data connection. |`EventsReceived` |Count |Total, Average, Minimum, Maximum |`ComponentType`, `ComponentName`|PT1M |Yes|
|**Export Utilization**<p><p>Export utilization |`ExportUtilization` |Percent |Maximum |\<none\>|PT1M |Yes|
|**FollowerLatency**<p><p>The follower databases synchronize changes in the leader databases. Because of the synchronization, there's a data lag of a few seconds to a few minutes in data availability.This metric measures the length of the time lag. The time lag depends on the overall size of the leader database metadata.This is a cluster level metrics: the followers catch metadata of all databases that are followed. This metric represents the latency of the process. |`FollowerLatency` |MilliSeconds |Average, Maximum, Minimum |`State`, `RoleInstance`|PT1M |Yes|
|**Ingestion Latency**<p><p>Latency of data ingested, from the time the data was received in the cluster until it's ready for query. The ingestion latency period depends on the ingestion scenario. |`IngestionLatencyInSeconds` |Seconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Ingestion result**<p><p>Total number of sources that either failed or succeeded to be ingested. Splitting the metric by status, you can get detailed information about the status of the ingestion operations. |`IngestionResult` |Count |Total |`IngestionResultDetails`, `FailureKind`|PT1M |Yes|
|**Ingestion utilization**<p><p>Ratio of used ingestion slots in the cluster |`IngestionUtilization` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Ingestion Volume**<p><p>Overall volume of ingested data to the cluster |`IngestionVolumeInMB` |Bytes |Total, Maximum |`Database`|PT1M |Yes|
|**Instance Count**<p><p>Total instance count |`InstanceCount` |Count |Average, Maximum, Minimum, Count, Total |\<none\>|PT1M |Yes|
|**Keep alive**<p><p>Sanity check indicates the cluster responds to queries |`KeepAlive` |Count |Average |\<none\>|PT1M |Yes|
|**Materialized View Age**<p><p>The materialized view age in minutes |`MaterializedViewAgeMinutes` |Count |Average |`Database`, `MaterializedViewName`|PT1M |Yes|
|**Materialized View Age**<p><p>The materialized view age in seconds |`MaterializedViewAgeSeconds` |Seconds |Average, Minimum, Maximum |`Database`, `MaterializedViewName`|PT1M |Yes|
|**Materialized View Data Loss**<p><p>Indicates potential data loss in materialized view |`MaterializedViewDataLoss` |Count |Maximum |`Database`, `MaterializedViewName`, `Kind`|PT1M |Yes|
|**Materialized View Extents Rebuild**<p><p>Number of extents rebuild |`MaterializedViewExtentsRebuild` |Count |Average |`Database`, `MaterializedViewName`|PT1M |Yes|
|**Materialized View Health**<p><p>The health of the materialized view (1 for healthy, 0 for non-healthy) |`MaterializedViewHealth` |Count |Average |`Database`, `MaterializedViewName`|PT1M |Yes|
|**Materialized View Records In Delta**<p><p>The number of records in the non-materialized part of the view |`MaterializedViewRecordsInDelta` |Count |Average |`Database`, `MaterializedViewName`|PT1M |Yes|
|**Materialized View Result**<p><p>The result of the materialization process |`MaterializedViewResult` |Count |Average |`Database`, `MaterializedViewName`, `Result`|PT1M |Yes|
|**Query duration**<p><p>Queries duration in seconds |`QueryDuration` |MilliSeconds |Average, Maximum, Minimum, Total |`QueryStatus`|PT1M |Yes|
|**Query Result**<p><p>Total number of queries. |`QueryResult` |Count |Count |`QueryStatus`|PT1M |No|
|**Queue Length**<p><p>Number of pending messages in a component's queue. |`QueueLength` |Count |Average |`ComponentType`|PT1M |Yes|
|**Queue Oldest Message**<p><p>Time in seconds from when the oldest message in queue was inserted. |`QueueOldestMessage` |Count |Average |`ComponentType`|PT1M |Yes|
|**Received Data Size Bytes**<p><p>Size of data received by data connection. This is the size of the data stream, or of raw data size if provided. |`ReceivedDataSizeBytes` |Bytes |Average, Total |`ComponentType`, `ComponentName`|PT1M |Yes|
|**Stage Latency**<p><p>Cumulative time from when a message is discovered until it is received by the reporting component for processing (discovery time is set when message is enqueued for ingestion queue, or when discovered by data connection). |`StageLatency` |Seconds |Average |`Database`, `ComponentType`|PT1M |Yes|
|**Streaming Ingest Data Rate**<p><p>Streaming ingest data rate |`StreamingIngestDataRate` |Bytes |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**Streaming Ingest Duration**<p><p>Streaming ingest duration in milliseconds |`StreamingIngestDuration` |MilliSeconds |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**Streaming Ingest Result**<p><p>Streaming ingest result |`StreamingIngestResults` |Count |Count |`Result`|PT1M |Yes|
|**Total number of concurrent queries**<p><p>Total number of concurrent queries |`TotalNumberOfConcurrentQueries` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Total number of extents**<p><p>Total number of data extents |`TotalNumberOfExtents` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Total number of throttled commands**<p><p>Total number of throttled commands |`TotalNumberOfThrottledCommands` |Count |Average, Maximum, Minimum, Total |`CommandType`|PT1M |Yes|
|**Total number of throttled queries**<p><p>Total number of throttled queries |`TotalNumberOfThrottledQueries` |Count |Average, Maximum, Minimum, Total |\<none\>|PT1M |Yes|
|**Weak consistency latency**<p><p>The max latency between the previous metadata sync and the next one (in DB/node scope) |`WeakConsistencyLatency` |Seconds |Average, Maximum, Minimum |`Database`, `RoleInstance`|PT1M |Yes|