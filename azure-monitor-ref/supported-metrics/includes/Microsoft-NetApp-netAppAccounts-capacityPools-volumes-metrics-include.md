---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NetApp/netAppAccounts/capacityPools/volumes, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Average read latency<p><p>Average read latency in milliseconds per operation |`AverageReadLatency` |MilliSeconds |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Average write latency<p><p>Average write latency in milliseconds per operation |`AverageWriteLatency` |MilliSeconds |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Is Volume Backup suspended<p><p>Is the backup policy suspended for the volume? 0 if yes, 1 if no. |`CbsVolumeBackupActive` |Count |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume Backup Bytes<p><p>Total bytes backed up for this Volume. |`CbsVolumeLogicalBackupBytes` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume Backup Operation Last Transferred Bytes<p><p>Total bytes transferred for last backup operation. |`CbsVolumeOperationBackupTransferredBytes` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Is Volume Backup Operation Complete<p><p>Did the last volume backup or restore operation complete successfully? 1 if yes, 0 if no. |`CbsVolumeOperationComplete` |Count |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume Backup Restore Operation Last Transferred Bytes<p><p>Total bytes transferred for last backup restore operation. |`CbsVolumeOperationRestoreTransferredBytes` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume Backup Last Transferred Bytes<p><p>Total bytes transferred for last backup or restore operation. |`CbsVolumeOperationTransferredBytes` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Is Volume Backup Enabled<p><p>Is backup enabled for the volume? 1 if yes, 0 if no. |`CbsVolumeProtected` |Count |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Other throughput<p><p>Other throughput (that is not read or write) in bytes per second |`OtherThroughput` |BytesPerSecond |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Read iops<p><p>Read In/out operations per second |`ReadIops` |CountPerSecond |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Read throughput<p><p>Read throughput in bytes per second |`ReadThroughput` |BytesPerSecond |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Throughput limit reached<p><p>Has the throughput limit been reached, 1 if it has and 0 if not. |`ThroughputLimitReached` |Count |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Total throughput<p><p>Sum of all throughput in bytes per second |`TotalThroughput` |BytesPerSecond |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume allocated size<p><p>The provisioned size of a volume |`VolumeAllocatedSize` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Percentage Volume Consumed Size<p><p>The percentage of the volume consumed including snapshots. |`VolumeConsumedSizePercentage` |Percent |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume cool tier data read size<p><p>Data read in using GET per volume |`VolumeCoolTierDataReadSize` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume cool tier data write size<p><p>Data tiered out using PUT per volume |`VolumeCoolTierDataWriteSize` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume cool tier size<p><p>Volume Footprint for Cool Tier |`VolumeCoolTierSize` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume Consumed Size<p><p>Logical size of the volume (used bytes) |`VolumeLogicalSize` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume snapshot size<p><p>Size of all snapshots in volume |`VolumeSnapshotSize` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Write iops<p><p>Write In/out operations per second |`WriteIops` |CountPerSecond |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Write throughput<p><p>Write throughput in bytes per second |`WriteThroughput` |BytesPerSecond |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Is volume replication status healthy<p><p>Condition of the relationship, 1 or 0. |`XregionReplicationHealthy` |Count |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume replication lag time<p><p>The amount of time in seconds by which the data on the mirror lags behind the source. |`XregionReplicationLagTime` |Seconds |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume replication last transfer duration<p><p>The amount of time in seconds it took for the last transfer to complete. |`XregionReplicationLastTransferDuration` |Seconds |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume replication last transfer size<p><p>The total number of bytes transferred as part of the last transfer. |`XregionReplicationLastTransferSize` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume replication progress<p><p>Total amount of data transferred for the current transfer operation. |`XregionReplicationRelationshipProgress` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Is volume replication transferring<p><p>Whether the status of the Volume Replication is 'transferring'. |`XregionReplicationRelationshipTransferring` |Count |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Volume replication total transfer<p><p>Cumulative bytes transferred for the relationship. |`XregionReplicationTotalTransferBytes` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|