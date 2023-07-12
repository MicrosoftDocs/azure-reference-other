---
title: Supported metrics - microsoft.compute/disks
description: Reference for microsoft.compute/disks metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.compute/disks  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.compute/disks resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Disk Read Bytes/sec(Preview)<p><p>Bytes/sec read from disk during monitoring period, please note, this metric is in preview and is subject to change before becoming generally available |`Composite Disk Read Bytes/sec` |BytesPerSecond |Average |No Dimensions |No|
|Disk Read Operations/sec(Preview)<p><p>Number of read IOs performed on a disk during monitoring period, please note, this metric is in preview and is subject to change before becoming generally available |`Composite Disk Read Operations/sec` |CountPerSecond |Average |No Dimensions |No|
|Disk Write Bytes/sec(Preview)<p><p>Bytes/sec written to disk during monitoring period, please note, this metric is in preview and is subject to change before becoming generally available |`Composite Disk Write Bytes/sec` |BytesPerSecond |Average |No Dimensions |No|
|Disk Write Operations/sec(Preview)<p><p>Number of Write IOs performed on a disk during monitoring period, please note, this metric is in preview and is subject to change before becoming generally available |`Composite Disk Write Operations/sec` |CountPerSecond |Average |No Dimensions |No|
|Disk On-demand Burst Operations(Preview)<p><p>The accumulated operations of burst transactions used for disks with on-demand burst enabled. Emitted on an hour interval |`DiskPaidBurstIOPS` |Count |Average |No Dimensions |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->