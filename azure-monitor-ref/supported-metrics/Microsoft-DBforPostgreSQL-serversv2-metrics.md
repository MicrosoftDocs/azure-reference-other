---
title: Supported metrics - Microsoft.DBforPostgreSQL/serversv2
description: Reference for Microsoft.DBforPostgreSQL/serversv2 metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.DBforPostgreSQL/serversv2  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.DBforPostgreSQL/serversv2 resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Active Connections<p><p>Active Connections |`active_connections` |Count |Average |No Dimensions |Yes|
|CPU percent<p><p>CPU percent |`cpu_percent` |Percent |Average |No Dimensions |Yes|
|IOPS<p><p>IO Operations per second |`iops` |Count |Average |No Dimensions |Yes|
|Memory percent<p><p>Memory percent |`memory_percent` |Percent |Average |No Dimensions |Yes|
|Network Out<p><p>Network Out across active connections |`network_bytes_egress` |Bytes |Total |No Dimensions |Yes|
|Network In<p><p>Network In across active connections |`network_bytes_ingress` |Bytes |Total |No Dimensions |Yes|
|Storage percent<p><p>Storage percent |`storage_percent` |Percent |Average |No Dimensions |Yes|
|Storage used<p><p>Storage used |`storage_used` |Bytes |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->