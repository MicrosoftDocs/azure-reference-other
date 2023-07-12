---
title: Supported metrics - Microsoft.ClassicCompute/domainNames/slots/roles
description: Reference for Microsoft.ClassicCompute/domainNames/slots/roles metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.ClassicCompute/domainNames/slots/roles  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.ClassicCompute/domainNames/slots/roles resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Disk Read<p><p>Average bytes read from disk during monitoring period. |`Disk Read Bytes/Sec` |BytesPerSecond |Average |RoleInstanceId |No|
|Disk Read Operations/Sec<p><p>Disk Read IOPS. |`Disk Read Operations/Sec` |CountPerSecond |Average |RoleInstanceId |Yes|
|Disk Write<p><p>Average bytes written to disk during monitoring period. |`Disk Write Bytes/Sec` |BytesPerSecond |Average |RoleInstanceId |No|
|Disk Write Operations/Sec<p><p>Disk Write IOPS. |`Disk Write Operations/Sec` |CountPerSecond |Average |RoleInstanceId |Yes|
|Network In<p><p>The number of bytes received on all network interfaces by the Virtual Machine(s) (Incoming Traffic). |`Network In` |Bytes |Total |RoleInstanceId |Yes|
|Network Out<p><p>The number of bytes out on all network interfaces by the Virtual Machine(s) (Outgoing Traffic). |`Network Out` |Bytes |Total |RoleInstanceId |Yes|
|Percentage CPU<p><p>The percentage of allocated compute units that are currently in use by the Virtual Machine(s). |`Percentage CPU` |Percent |Average |RoleInstanceId |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->