---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.StorageSync/storageSyncServices, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Sync Session Result**<br><br>Metric that logs a value of 1 each time the Server Endpoint successfully completes a Sync Session with the Cloud Endpoint |`ServerSyncSessionResult` |Count |Average, Count, Total, Maximum, Minimum |`SyncGroupName`, `ServerEndpointName`, `SyncDirection`|PT1M |Yes|
|**Bytes synced**<br><br>Total file size transferred for Sync Sessions |`StorageSyncBatchTransferredFileBytes` |Bytes |Average, Total |`SyncGroupName`, `ServerEndpointName`, `SyncDirection`|PT1M |Yes|
|**Cloud tiering cache hit rate**<br><br>Percentage of bytes that were served from the cache |`StorageSyncComputedCacheHitRate` |Percent |Average |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|
|**Cache data size by last access time**<br><br>Size of data by last access time |`StorageSyncDataSizeByAccessPattern` |Bytes |Average, Maximum, Minimum |`SyncGroupName`, `ServerName`, `ServerEndpointName`, `LastAccessTime`|PT1M |No|
|**Cloud tiering size of data tiered by last maintenance job**<br><br>Size of data tiered during last maintenance job |`StorageSyncIncrementalTieredDataSizeBytes` |Bytes |Total, Average, Maximum, Minimum |`SyncGroupName`, `ServerName`, `ServerEndpointName`, `TieringReason`|PT1M |Yes|
|**Cloud tiering low disk space mode**<br><br>Indicates if the server endpoint is in low disk space mode or not (1=yes; 0=no) |`StorageSyncLowDiskModeCount` |Count |Count, Minimum, Maximum, Total |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|
|**Cloud tiering recall success rate**<br><br>Percentage of all recalls that were successful |`StorageSyncRecallComputedSuccessRate` |Percent |Average |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|
|**Cloud tiering recall size by application**<br><br>Size of data recalled by application |`StorageSyncRecalledNetworkBytesByApplication` |Bytes |Average, Total |`SyncGroupName`, `ServerName`, `ApplicationName`|PT1M |Yes|
|**Cloud tiering recall size**<br><br>Size of data recalled |`StorageSyncRecalledTotalNetworkBytes` |Bytes |Average, Total |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|
|**Cloud tiering recall throughput**<br><br>Size of data recall throughput |`StorageSyncRecallThroughputBytesPerSecond` |BytesPerSecond |Average, Total, Maximum, Minimum |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|
|**Server Online Status**<br><br>Metric that logs a value of 1 each time the resigtered server successfully records a heartbeat with the Cloud Endpoint |`StorageSyncServerHeartbeat` |Count |Average, Count, Total, Maximum, Minimum |`ServerName`|PT1M |Yes|
|**Files Synced**<br><br>Count of Files synced |`StorageSyncSyncSessionAppliedFilesCount` |Count |Average, Total |`SyncGroupName`, `ServerEndpointName`, `SyncDirection`|PT1M |Yes|
|**Files not syncing**<br><br>Count of files failed to sync |`StorageSyncSyncSessionPerItemErrorsCount` |Count |Average |`SyncGroupName`, `ServerEndpointName`, `SyncDirection`|PT1M |Yes|
|**Cloud tiering size of data tiered**<br><br>Size of data tiered to Azure file share |`StorageSyncTieredDataSizeBytes` |Bytes |Average, Total, Maximum, Minimum |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|
|**Server cache size**<br><br>Size of data cached on the server |`StorageSyncTieringCacheSizeBytes` |Bytes |Average, Maximum, Minimum |`SyncGroupName`, `ServerName`, `ServerEndpointName`|PT1M |Yes|