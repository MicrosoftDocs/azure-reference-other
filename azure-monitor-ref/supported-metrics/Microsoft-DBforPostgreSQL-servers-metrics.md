---
title: Supported metrics - Microsoft.DBforPostgreSQL/servers
description: Reference for Microsoft.DBforPostgreSQL/servers metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.DBforPostgreSQL/servers  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.DBforPostgreSQL/servers resource type.

  

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
|Backup Storage Used<p><p>Backup Storage Used |`backup_storage_used` |Bytes |Average |No Dimensions |Yes|
|Failed Connections<p><p>Failed Connections |`connections_failed` |Count |Total |No Dimensions |Yes|
|CPU percent<p><p>CPU percent |`cpu_percent` |Percent |Average |No Dimensions |Yes|
|IO percent<p><p>IO percent |`io_consumption_percent` |Percent |Average |No Dimensions |Yes|
|Memory percent<p><p>Memory percent |`memory_percent` |Percent |Average |No Dimensions |Yes|
|Network Out<p><p>Network Out across active connections |`network_bytes_egress` |Bytes |Total |No Dimensions |Yes|
|Network In<p><p>Network In across active connections |`network_bytes_ingress` |Bytes |Total |No Dimensions |Yes|
|Max Lag Across Replicas<p><p>Lag in bytes of the most lagging replica |`pg_replica_log_delay_in_bytes` |Bytes |Maximum |No Dimensions |Yes|
|Replica Lag<p><p>Replica lag in seconds |`pg_replica_log_delay_in_seconds` |Seconds |Maximum |No Dimensions |Yes|
|Server Log storage limit<p><p>Server Log storage limit |`serverlog_storage_limit` |Bytes |Maximum |No Dimensions |Yes|
|Server Log storage percent<p><p>Server Log storage percent |`serverlog_storage_percent` |Percent |Average |No Dimensions |Yes|
|Server Log storage used<p><p>Server Log storage used |`serverlog_storage_usage` |Bytes |Average |No Dimensions |Yes|
|Storage limit<p><p>Storage limit |`storage_limit` |Bytes |Maximum |No Dimensions |Yes|
|Storage percent<p><p>Storage percent |`storage_percent` |Percent |Average |No Dimensions |Yes|
|Storage used<p><p>Storage used |`storage_used` |Bytes |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->