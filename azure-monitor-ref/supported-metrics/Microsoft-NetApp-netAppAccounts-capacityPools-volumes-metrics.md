---
title: Supported metrics - Microsoft.NetApp/netAppAccounts/capacityPools/volumes
description: Reference for Microsoft.NetApp/netAppAccounts/capacityPools/volumes metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.NetApp/netAppAccounts/capacityPools/volumes  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.NetApp/netAppAccounts/capacityPools/volumes resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Average read latency<p><p>Average read latency in milliseconds per operation |`AverageReadLatency` |MilliSeconds |Average |No Dimensions |Yes|
|Average write latency<p><p>Average write latency in milliseconds per operation |`AverageWriteLatency` |MilliSeconds |Average |No Dimensions |Yes|
|Is Volume Backup suspended<p><p>Is the backup policy suspended for the volume? 0 if yes, 1 if no. |`CbsVolumeBackupActive` |Count |Average |No Dimensions |Yes|
|Volume Backup Bytes<p><p>Total bytes backed up for this Volume. |`CbsVolumeLogicalBackupBytes` |Bytes |Average |No Dimensions |Yes|
|Volume Backup Operation Last Transferred Bytes<p><p>Total bytes transferred for last backup operation. |`CbsVolumeOperationBackupTransferredBytes` |Bytes |Average |No Dimensions |Yes|
|Is Volume Backup Operation Complete<p><p>Did the last volume backup or restore operation complete successfully? 1 if yes, 0 if no. |`CbsVolumeOperationComplete` |Count |Average |No Dimensions |Yes|
|Volume Backup Restore Operation Last Transferred Bytes<p><p>Total bytes transferred for last backup restore operation. |`CbsVolumeOperationRestoreTransferredBytes` |Bytes |Average |No Dimensions |Yes|
|Volume Backup Last Transferred Bytes<p><p>Total bytes transferred for last backup or restore operation. |`CbsVolumeOperationTransferredBytes` |Bytes |Average |No Dimensions |Yes|
|Is Volume Backup Enabled<p><p>Is backup enabled for the volume? 1 if yes, 0 if no. |`CbsVolumeProtected` |Count |Average |No Dimensions |Yes|
|Other throughput<p><p>Other throughput (that is not read or write) in bytes per second |`OtherThroughput` |BytesPerSecond |Average |No Dimensions |Yes|
|Read iops<p><p>Read In/out operations per second |`ReadIops` |CountPerSecond |Average |No Dimensions |Yes|
|Read throughput<p><p>Read throughput in bytes per second |`ReadThroughput` |BytesPerSecond |Average |No Dimensions |Yes|
|Total throughput<p><p>Sum of all throughput in bytes per second |`TotalThroughput` |BytesPerSecond |Average |No Dimensions |Yes|
|Volume allocated size<p><p>The provisioned size of a volume |`VolumeAllocatedSize` |Bytes |Average |No Dimensions |Yes|
|Percentage Volume Consumed Size<p><p>The percentage of the volume consumed including snapshots. |`VolumeConsumedSizePercentage` |Percent |Average |No Dimensions |Yes|
|Volume cool tier data read size<p><p>Data read in using GET per volume |`VolumeCoolTierDataReadSize` |Bytes |Average |No Dimensions |Yes|
|Volume cool tier data write size<p><p>Data tiered out using PUT per volume |`VolumeCoolTierDataWriteSize` |Bytes |Average |No Dimensions |Yes|
|Volume cool tier size<p><p>Volume Footprint for Cool Tier |`VolumeCoolTierSize` |Bytes |Average |No Dimensions |Yes|
|Volume Consumed Size<p><p>Logical size of the volume (used bytes) |`VolumeLogicalSize` |Bytes |Average |No Dimensions |Yes|
|Volume snapshot size<p><p>Size of all snapshots in volume |`VolumeSnapshotSize` |Bytes |Average |No Dimensions |Yes|
|Write iops<p><p>Write In/out operations per second |`WriteIops` |CountPerSecond |Average |No Dimensions |Yes|
|Write throughput<p><p>Write throughput in bytes per second |`WriteThroughput` |BytesPerSecond |Average |No Dimensions |Yes|
|Is volume replication status healthy<p><p>Condition of the relationship, 1 or 0. |`XregionReplicationHealthy` |Count |Average |No Dimensions |Yes|
|Volume replication lag time<p><p>The amount of time in seconds by which the data on the mirror lags behind the source. |`XregionReplicationLagTime` |Seconds |Average |No Dimensions |Yes|
|Volume replication last transfer duration<p><p>The amount of time in seconds it took for the last transfer to complete. |`XregionReplicationLastTransferDuration` |Seconds |Average |No Dimensions |Yes|
|Volume replication last transfer size<p><p>The total number of bytes transferred as part of the last transfer. |`XregionReplicationLastTransferSize` |Bytes |Average |No Dimensions |Yes|
|Volume replication progress<p><p>Total amount of data transferred for the current transfer operation. |`XregionReplicationRelationshipProgress` |Bytes |Average |No Dimensions |Yes|
|Is volume replication transferring<p><p>Whether the status of the Volume Replication is 'transferring'. |`XregionReplicationRelationshipTransferring` |Count |Average |No Dimensions |Yes|
|Volume replication total transfer<p><p>Cumulative bytes transferred for the relationship. |`XregionReplicationTotalTransferBytes` |Bytes |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->