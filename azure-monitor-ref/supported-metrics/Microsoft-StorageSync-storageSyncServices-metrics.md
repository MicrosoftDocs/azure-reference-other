---
title: Supported metrics - Microsoft.StorageSync/storageSyncServices
description: Reference for Microsoft.StorageSync/storageSyncServices metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.StorageSync/storageSyncServices  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.StorageSync/storageSyncServices resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Sync Session Result<p><p>Metric that logs a value of 1 each time the Server Endpoint successfully completes a Sync Session with the Cloud Endpoint |`ServerSyncSessionResult` |Count |Average |SyncGroupName, ServerEndpointName, SyncDirection |Yes|
|Bytes synced<p><p>Total file size transferred for Sync Sessions |`StorageSyncBatchTransferredFileBytes` |Bytes |Total |SyncGroupName, ServerEndpointName, SyncDirection |Yes|
|Cloud tiering cache hit rate<p><p>Percentage of bytes that were served from the cache |`StorageSyncComputedCacheHitRate` |Percent |Average |SyncGroupName, ServerName, ServerEndpointName |Yes|
|Cache data size by last access time<p><p>Size of data by last access time |`StorageSyncDataSizeByAccessPattern` |Bytes |Average |SyncGroupName, ServerName, ServerEndpointName, LastAccessTime |No|
|Cloud tiering size of data tiered by last maintenance job<p><p>Size of data tiered during last maintenance job |`StorageSyncIncrementalTieredDataSizeBytes` |Bytes |Total |SyncGroupName, ServerName, ServerEndpointName, TieringReason |Yes|
|Cloud tiering recall success rate<p><p>Percentage of all recalls that were successful |`StorageSyncRecallComputedSuccessRate` |Percent |Average |SyncGroupName, ServerName, ServerEndpointName |Yes|
|Cloud tiering recall size by application<p><p>Size of data recalled by application |`StorageSyncRecalledNetworkBytesByApplication` |Bytes |Total |SyncGroupName, ServerName, ApplicationName |Yes|
|Cloud tiering recall size<p><p>Size of data recalled |`StorageSyncRecalledTotalNetworkBytes` |Bytes |Total |SyncGroupName, ServerName, ServerEndpointName |Yes|
|Cloud tiering recall throughput<p><p>Size of data recall throughput |`StorageSyncRecallThroughputBytesPerSecond` |BytesPerSecond |Average |SyncGroupName, ServerName, ServerEndpointName |Yes|
|Server Online Status<p><p>Metric that logs a value of 1 each time the resigtered server successfully records a heartbeat with the Cloud Endpoint |`StorageSyncServerHeartbeat` |Count |Maximum |ServerName |Yes|
|Files Synced<p><p>Count of Files synced |`StorageSyncSyncSessionAppliedFilesCount` |Count |Total |SyncGroupName, ServerEndpointName, SyncDirection |Yes|
|Files not syncing<p><p>Count of files failed to sync |`StorageSyncSyncSessionPerItemErrorsCount` |Count |Average |SyncGroupName, ServerEndpointName, SyncDirection |Yes|
|Cloud tiering size of data tiered<p><p>Size of data tiered to Azure file share |`StorageSyncTieredDataSizeBytes` |Bytes |Average |SyncGroupName, ServerName, ServerEndpointName |Yes|
|Server cache size<p><p>Size of data cached on the server |`StorageSyncTieringCacheSizeBytes` |Bytes |Average |SyncGroupName, ServerName, ServerEndpointName |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->