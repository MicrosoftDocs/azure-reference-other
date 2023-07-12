---
title: Supported metrics - Microsoft.Compute/cloudServices/roles
description: Reference for Microsoft.Compute/cloudServices/roles metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Compute/cloudServices/roles  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.Compute/cloudServices/roles resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Available Memory Bytes (Preview)<p><p>Amount of physical memory, in bytes, immediately available for allocation to a process or for system use in the Virtual Machine |`Available Memory Bytes` |Bytes |Average |RoleInstanceId, RoleId |Yes|
|Disk Read Bytes<p><p>Bytes read from disk during monitoring period |`Disk Read Bytes` |Bytes |Total |RoleInstanceId, RoleId |Yes|
|Disk Read Operations/Sec<p><p>Disk Read IOPS |`Disk Read Operations/Sec` |CountPerSecond |Average |RoleInstanceId, RoleId |Yes|
|Disk Write Bytes<p><p>Bytes written to disk during monitoring period |`Disk Write Bytes` |Bytes |Total |RoleInstanceId, RoleId |Yes|
|Disk Write Operations/Sec<p><p>Disk Write IOPS |`Disk Write Operations/Sec` |CountPerSecond |Average |RoleInstanceId, RoleId |Yes|
|Network In Total<p><p>The number of bytes received on all network interfaces by the Virtual Machine(s) (Incoming Traffic) |`Network In Total` |Bytes |Total |RoleInstanceId, RoleId |Yes|
|Network Out Total<p><p>The number of bytes out on all network interfaces by the Virtual Machine(s) (Outgoing Traffic) |`Network Out Total` |Bytes |Total |RoleInstanceId, RoleId |Yes|
|Percentage CPU<p><p>The percentage of allocated compute units that are currently in use by the Virtual Machine(s) |`Percentage CPU` |Percent |Average |RoleInstanceId, RoleId |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->