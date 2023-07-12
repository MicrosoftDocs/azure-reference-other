---
title: Supported metrics - Microsoft.DocumentDB/mongoClusters
description: Reference for Microsoft.DocumentDB/mongoClusters metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.DocumentDB/mongoClusters  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.DocumentDB/mongoClusters resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Committed Memory percent<p><p>Percentage of Commit Memory Limit allocated by applications on node |`CommittedMemoryPercent` |Percent |Average |ServerName |No|
|CPU percent<p><p>Percent CPU utilization on node |`CpuPercent` |Percent |Average |ServerName |No|
|IOPS<p><p>Disk IO operations per second on node |`IOPS` |Count |Average |ServerName |Yes|
|Memory percent<p><p>Percent memory utilization on node |`MemoryPercent` |Percent |Average |ServerName |No|
|Storage percent<p><p>Percent of available storage used on node |`StoragePercent` |Percent |Average |ServerName |No|
|Storage used<p><p>Quantity of available storage used on node |`StorageUsed` |Bytes |Average |ServerName |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->