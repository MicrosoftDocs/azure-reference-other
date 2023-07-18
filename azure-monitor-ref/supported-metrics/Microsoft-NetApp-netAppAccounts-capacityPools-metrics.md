---
title: Supported metrics - Microsoft.NetApp/netAppAccounts/capacityPools
description: Reference for Microsoft.NetApp/netAppAccounts/capacityPools metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.NetApp/netAppAccounts/capacityPools  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.NetApp/netAppAccounts/capacityPools resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Pool Allocated Size<p><p>Provisioned size of this pool |`VolumePoolAllocatedSize` |Bytes |Average |No Dimensions |Yes|
|Pool allocated throughput<p><p>Sum of the throughput of all the volumes belonging to the pool |`VolumePoolAllocatedToVolumeThroughput` |BytesPerSecond |Average |No Dimensions |Yes|
|Pool Allocated To Volume Size<p><p>Allocated used size of the pool |`VolumePoolAllocatedUsed` |Bytes |Average |No Dimensions |Yes|
|Provisioned throughput for the pool<p><p>Provisioned throughput of this pool |`VolumePoolProvisionedThroughput` |BytesPerSecond |Average |No Dimensions |Yes|
|Pool Consumed Size<p><p>Sum of the logical size of all the volumes belonging to the pool |`VolumePoolTotalLogicalSize` |Bytes |Average |No Dimensions |Yes|
|Total Snapshot size for the pool<p><p>Sum of snapshot size of all volumes in this pool |`VolumePoolTotalSnapshotSize` |Bytes |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->