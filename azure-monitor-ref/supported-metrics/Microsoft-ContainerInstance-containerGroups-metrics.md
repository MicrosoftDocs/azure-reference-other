---
title: Supported metrics - Microsoft.ContainerInstance/containerGroups
description: Reference for Microsoft.ContainerInstance/containerGroups metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.ContainerInstance/containerGroups  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.ContainerInstance/containerGroups resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|CPU Usage<p><p>CPU usage on all cores in millicores. |`CpuUsage` |Count |Average |containerName |Yes|
|Memory Usage<p><p>Total memory usage in byte. |`MemoryUsage` |Bytes |Average |containerName |Yes|
|Network Bytes Received Per Second<p><p>The network bytes received per second. |`NetworkBytesReceivedPerSecond` |Bytes |Average |No Dimensions |Yes|
|Network Bytes Transmitted Per Second<p><p>The network bytes transmitted per second. |`NetworkBytesTransmittedPerSecond` |Bytes |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->