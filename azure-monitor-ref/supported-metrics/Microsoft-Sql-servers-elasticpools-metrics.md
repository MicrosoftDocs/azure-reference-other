---
title: Supported metrics - Microsoft.Sql/servers/elasticpools
description: Reference for Microsoft.Sql/servers/elasticpools metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Sql/servers/elasticpools  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Sql/servers/elasticpools resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Data space allocated<p><p>Data space allocated. Not applicable to hyperscale |`allocated_data_storage` |Bytes |Average |No Dimensions |Yes|
|Data space allocated percent<p><p>Data space allocated percent. Not applicable to hyperscale |`allocated_data_storage_percent` |Percent |Maximum |No Dimensions |Yes|
|App CPU billed<p><p>App CPU billed. Applies to serverless elastic pools. |`app_cpu_billed` |Count |Total |No Dimensions |Yes|
|App CPU percentage<p><p>App CPU percentage. Applies to serverless elastic pools. |`app_cpu_percent` |Percent |Average |No Dimensions |Yes|
|App memory percentage<p><p>App memory percentage. Applies to serverless elastic pools. |`app_memory_percent` |Percent |Average |No Dimensions |Yes|
|CPU limit<p><p>CPU limit. Applies to vCore-based elastic pools. |`cpu_limit` |Count |Average |No Dimensions |Yes|
|CPU percentage<p><p>CPU percentage |`cpu_percent` |Percent |Average |No Dimensions |Yes|
|CPU used<p><p>CPU used. Applies to vCore-based elastic pools. |`cpu_used` |Count |Average |No Dimensions |Yes|
|DTU percentage<p><p>DTU Percentage. Applies to DTU-based elastic pools. |`dtu_consumption_percent` |Percent |Average |No Dimensions |Yes|
|eDTU limit<p><p>eDTU limit. Applies to DTU-based elastic pools. |`eDTU_limit` |Count |Average |No Dimensions |Yes|
|eDTU used<p><p>eDTU used. Applies to DTU-based elastic pools. |`eDTU_used` |Count |Average |No Dimensions |Yes|
|Log IO percentage<p><p>Log IO percentage |`log_write_percent` |Percent |Average |No Dimensions |Yes|
|Data IO percentage<p><p>Data IO percentage |`physical_data_read_percent` |Percent |Average |No Dimensions |Yes|
|Sessions Count<p><p>Number of active sessions |`sessions_count` |Count |Average |No Dimensions |Yes|
|Sessions percentage<p><p>Sessions percentage |`sessions_percent` |Percent |Average |No Dimensions |Yes|
|SQL instance CPU percent<p><p>CPU usage by all user and system workloads. Applies to elastic pools. |`sql_instance_cpu_percent` |Percent |Maximum |No Dimensions |Yes|
|SQL instance memory percent<p><p>Memory usage by the database engine instance. Applies to elastic pools. |`sql_instance_memory_percent` |Percent |Maximum |No Dimensions |Yes|
|SQL Server process core percent<p><p>CPU usage as a percentage of the SQL DB process. Applies to elastic pools. (This metric is equivalent to sql_instance_cpu_percent, and will be removed in the future.) |`sqlserver_process_core_percent` |Percent |Maximum |No Dimensions |Yes|
|SQL Server process memory percent<p><p>Memory usage as a percentage of the SQL DB process. Applies to elastic pools. (This metric is equivalent to sql_instance_memory_percent, and will be removed in the future.) |`sqlserver_process_memory_percent` |Percent |Maximum |No Dimensions |Yes|
|Data max size<p><p>Data max size. Not applicable to hyperscale |`storage_limit` |Bytes |Average |No Dimensions |Yes|
|Data space used percent<p><p>Data space used percent. Not applicable to hyperscale |`storage_percent` |Percent |Average |No Dimensions |Yes|
|Data space used<p><p>Data space used. Not applicable to hyperscale |`storage_used` |Bytes |Average |No Dimensions |Yes|
|Tempdb Data File Size Kilobytes<p><p>Space used in tempdb data files in kilobytes. |`tempdb_data_size` |Count |Maximum |No Dimensions |Yes|
|Tempdb Log File Size Kilobytes<p><p>Space used in tempdb transaction log file in kilobytes. |`tempdb_log_size` |Count |Maximum |No Dimensions |Yes|
|Tempdb Percent Log Used<p><p>Space used percentage in tempdb transaction log file |`tempdb_log_used_percent` |Percent |Maximum |No Dimensions |Yes|
|Workers percentage<p><p>Workers percentage |`workers_percent` |Percent |Average |No Dimensions |Yes|
|In-Memory OLTP storage percent<p><p>In-Memory OLTP storage percent. Not applicable to hyperscale |`xtp_storage_percent` |Percent |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->