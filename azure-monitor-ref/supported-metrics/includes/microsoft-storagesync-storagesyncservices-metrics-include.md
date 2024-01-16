---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.StorageSync/storageSyncServices, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Sync Session Result**<p><p>Metric that logs a value of 1 each time the Server Endpoint successfully completes a Sync Session with the Cloud Endpoint |`ServerSyncSessionResult` |Count |Average, Count, Total, Maximum, Minimum |`SyncGroupName`, `ServerEndpointName`, `SyncDirection`|PT1M |Yes|
|**Bytes synced**<p><p>Total file size transferred for Sync Sessions |`StorageSyncBatchTransferredFileBytes` |Bytes |Average, Total |`SyncGroupName`, `ServerEndpointName`, `SyncDirection`|PT1M |Yes|
|**Cloud tiering cache hit rate**<p><p>Percentage of bytes that were served from the cache |`StorageSyncComputedCacheHitRate` |Percent |Average |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|
|**Cache data size by last access time**<p><p>Size of data by last access time |`StorageSyncDataSizeByAccessPattern` |Bytes |Average, Maximum, Minimum |`SyncGroupName`, `ServerName`, `ServerEndpointName`, `LastAccessTime`|PT1M |No|
|**Cloud tiering size of data tiered by last maintenance job**<p><p>Size of data tiered during last maintenance job |`StorageSyncIncrementalTieredDataSizeBytes` |Bytes |Total, Average, Maximum, Minimum |`SyncGroupName`, `ServerName`, `ServerEndpointName`, `TieringReason`|PT1M |Yes|
|**Cloud tiering low disk space mode**<p><p>Indicates if the server endpoint is in low disk space mode or not (1=yes; 0=no) |`StorageSyncLowDiskModeCount` |Count |Count, Minimum, Maximum, Total |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|
|**Cloud tiering recall success rate**<p><p>Percentage of all recalls that were successful |`StorageSyncRecallComputedSuccessRate` |Percent |Average |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|
|**Cloud tiering recall size by application**<p><p>Size of data recalled by application |`StorageSyncRecalledNetworkBytesByApplication` |Bytes |Average, Total |`SyncGroupName`, `ServerName`, `ApplicationName`|PT1M |Yes|
|**Cloud tiering recall size**<p><p>Size of data recalled |`StorageSyncRecalledTotalNetworkBytes` |Bytes |Average, Total |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|
|**Cloud tiering recall throughput**<p><p>Size of data recall throughput |`StorageSyncRecallThroughputBytesPerSecond` |BytesPerSecond |Average, Total, Maximum, Minimum |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|
|**Server Online Status**<p><p>Metric that logs a value of 1 each time the resigtered server successfully records a heartbeat with the Cloud Endpoint |`StorageSyncServerHeartbeat` |Count |Average, Count, Total, Maximum, Minimum |`ServerName`|PT1M |Yes|
|**Files Synced**<p><p>Count of Files synced |`StorageSyncSyncSessionAppliedFilesCount` |Count |Average, Total |`SyncGroupName`, `ServerEndpointName`, `SyncDirection`|PT1M |Yes|
|**Files not syncing**<p><p>Count of files failed to sync |`StorageSyncSyncSessionPerItemErrorsCount` |Count |Average |`SyncGroupName`, `ServerEndpointName`, `SyncDirection`|PT1M |Yes|
|**Cloud tiering size of data tiered**<p><p>Size of data tiered to Azure file share |`StorageSyncTieredDataSizeBytes` |Bytes |Average, Total, Maximum, Minimum |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|
|**Server cache size**<p><p>Size of data cached on the server |`StorageSyncTieringCacheSizeBytes` |Bytes |Average, Maximum, Minimum |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|