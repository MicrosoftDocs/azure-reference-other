---
title: Supported metrics - Microsoft.Sql/servers/databases
description: Reference for Microsoft.Sql/servers/databases metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Sql/servers/databases  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Sql/servers/databases resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Active queries<p><p>Active queries across all workload groups. Applies only to data warehouses. |`active_queries` |Count |Total |No Dimensions |Yes|
|Data space allocated<p><p>Allocated data storage. Not applicable to data warehouses. |`allocated_data_storage` |Bytes |Average |No Dimensions |Yes|
|App CPU billed<p><p>App CPU billed. Applies to serverless databases. |`app_cpu_billed` |Count |Total |No Dimensions |Yes|
|App CPU billed HA replicas<p><p>Sum of app CPU billed across all HA replicas associated with the primary replica or a named replica. |`app_cpu_billed_ha_replicas` |Count |Total |No Dimensions |Yes|
|App CPU percentage<p><p>App CPU percentage. Applies to serverless databases. |`app_cpu_percent` |Percent |Average |No Dimensions |Yes|
|App memory percentage<p><p>App memory percentage. Applies to serverless databases. |`app_memory_percent` |Percent |Average |No Dimensions |Yes|
|Data storage size<p><p>Data storage size. Applies to Hyperscale databases. |`base_blob_size_bytes` |Bytes |Maximum |No Dimensions |Yes|
|Blocked by Firewall<p><p>Blocked by Firewall |`blocked_by_firewall` |Count |Total |No Dimensions |Yes|
|Cache hit percentage<p><p>Cache hit percentage. Applies only to data warehouses. |`cache_hit_percent` |Percent |Maximum |No Dimensions |Yes|
|Cache used percentage<p><p>Cache used percentage. Applies only to data warehouses. |`cache_used_percent` |Percent |Maximum |No Dimensions |Yes|
|Failed Connections : System Errors<p><p>Failed Connections |`connection_failed` |Count |Total |Error |Yes|
|Failed Connections : User Errors<p><p>Failed Connections : User Errors |`connection_failed_user_error` |Count |Total |Error |Yes|
|Successful Connections<p><p>Successful Connections |`connection_successful` |Count |Total |SslProtocol |Yes|
|CPU limit<p><p>CPU limit. Applies to vCore-based databases. |`cpu_limit` |Count |Average |No Dimensions |Yes|
|CPU percentage<p><p>CPU percentage |`cpu_percent` |Percent |Average |No Dimensions |Yes|
|CPU used<p><p>CPU used. Applies to vCore-based databases. |`cpu_used` |Count |Average |No Dimensions |Yes|
|Deadlocks<p><p>Deadlocks. Not applicable to data warehouses. |`deadlock` |Count |Total |No Dimensions |Yes|
|Differential backup storage size<p><p>Cumulative differential backup storage size. Applies to vCore-based databases. Not applicable to Hyperscale databases. |`diff_backup_size_bytes` |Bytes |Maximum |No Dimensions |Yes|
|DTU percentage<p><p>DTU Percentage. Applies to DTU-based databases. |`dtu_consumption_percent` |Percent |Average |No Dimensions |Yes|
|DTU Limit<p><p>DTU Limit. Applies to DTU-based databases. |`dtu_limit` |Count |Average |No Dimensions |Yes|
|DTU used<p><p>DTU used. Applies to DTU-based databases. |`dtu_used` |Count |Average |No Dimensions |Yes|
|DWU percentage<p><p>DWU percentage. Applies only to data warehouses. |`dwu_consumption_percent` |Percent |Maximum |No Dimensions |Yes|
|DWU limit<p><p>DWU limit. Applies only to data warehouses. |`dwu_limit` |Count |Maximum |No Dimensions |Yes|
|DWU used<p><p>DWU used. Applies only to data warehouses. |`dwu_used` |Count |Maximum |No Dimensions |Yes|
|Free amount consumed<p><p>Free amount of vCore seconds consumed this month. Applies only to free database offer. |`free_amount_consumed` |Count |Maximum |No Dimensions |Yes|
|Free amount remaining<p><p>Free amount of vCore seconds remaining this month. Applies only to free database offer. |`free_amount_remaining` |Count |Minimum |No Dimensions |Yes|
|Full backup storage size<p><p>Cumulative full backup storage size. Applies to vCore-based databases. Not applicable to Hyperscale databases. |`full_backup_size_bytes` |Bytes |Maximum |No Dimensions |Yes|
|Failed Ledger Digest Uploads<p><p>Ledger digests that failed to be uploaded. |`ledger_digest_upload_failed` |Count |Count |No Dimensions |Yes|
|Successful Ledger Digest Uploads<p><p>Ledger digests that were successfully uploaded. |`ledger_digest_upload_success` |Count |Count |No Dimensions |Yes|
|Local tempdb percentage<p><p>Local tempdb percentage. Applies only to data warehouses. |`local_tempdb_usage_percent` |Percent |Average |No Dimensions |Yes|
|Log backup storage size<p><p>Cumulative log backup storage size. Applies to vCore-based and Hyperscale databases. |`log_backup_size_bytes` |Bytes |Maximum |No Dimensions |Yes|
|Log IO percentage<p><p>Log IO percentage. Not applicable to data warehouses. |`log_write_percent` |Percent |Average |No Dimensions |Yes|
|Memory percentage<p><p>Memory percentage. Applies only to data warehouses. |`memory_usage_percent` |Percent |Maximum |No Dimensions |Yes|
|Data IO percentage<p><p>Data IO percentage |`physical_data_read_percent` |Percent |Average |No Dimensions |Yes|
|Queued queries<p><p>Queued queries across all workload groups. Applies only to data warehouses. |`queued_queries` |Count |Total |No Dimensions |Yes|
|Sessions count<p><p>Number of active sessions. Not applicable to Synapse DW Analytics. |`sessions_count` |Count |Average |No Dimensions |Yes|
|Sessions percentage<p><p>Sessions percentage. Not applicable to data warehouses. |`sessions_percent` |Percent |Average |No Dimensions |Yes|
|Data backup storage size<p><p>Cumulative data backup storage size. Applies to Hyperscale databases. |`snapshot_backup_size_bytes` |Bytes |Maximum |No Dimensions |Yes|
|SQL instance CPU percent<p><p>CPU usage by all user and system workloads. Not applicable to data warehouses. |`sql_instance_cpu_percent` |Percent |Maximum |No Dimensions |Yes|
|SQL instance memory percent<p><p>Memory usage by the database engine instance. Not applicable to data warehouses. |`sql_instance_memory_percent` |Percent |Maximum |No Dimensions |Yes|
|SQL Server process core percent<p><p>CPU usage as a percentage of the SQL DB process. Not applicable to data warehouses. (This metric is equivalent to sql_instance_cpu_percent, and will be removed in the future.) |`sqlserver_process_core_percent` |Percent |Maximum |No Dimensions |Yes|
|SQL Server process memory percent<p><p>Memory usage as a percentage of the SQL DB process. Not applicable to data warehouses. (This metric is equivalent to sql_instance_memory_percent, and will be removed in the future.) |`sqlserver_process_memory_percent` |Percent |Maximum |No Dimensions |Yes|
|Data space used<p><p>Data space used. Not applicable to data warehouses. |`storage` |Bytes |Maximum |No Dimensions |Yes|
|Data space used percent<p><p>Data space used percent. Not applicable to data warehouses or hyperscale databases. |`storage_percent` |Percent |Maximum |No Dimensions |Yes|
|Tempdb Data File Size Kilobytes<p><p>Space used in tempdb data files in kilobytes. Not applicable to data warehouses. |`tempdb_data_size` |Count |Maximum |No Dimensions |Yes|
|Tempdb Log File Size Kilobytes<p><p>Space used in tempdb transaction log file in kilobytes. Not applicable to data warehouses. |`tempdb_log_size` |Count |Maximum |No Dimensions |Yes|
|Tempdb Percent Log Used<p><p>Space used percentage in tempdb transaction log file. Not applicable to data warehouses. |`tempdb_log_used_percent` |Percent |Maximum |No Dimensions |Yes|
|Workload group active queries<p><p>Active queries within the workload group. Applies only to data warehouses. |`wlg_active_queries` |Count |Total |WorkloadGroupName, IsUserDefined |Yes|
|Workload group query timeouts<p><p>Queries that have timed out for the workload group. Applies only to data warehouses. |`wlg_active_queries_timeouts` |Count |Total |WorkloadGroupName, IsUserDefined |Yes|
|Workload group allocation by system percent<p><p>Allocated percentage of resources relative to the entire system per workload group. Applies only to data warehouses. |`wlg_allocation_relative_to_system_percent` |Percent |Maximum |WorkloadGroupName, IsUserDefined |Yes|
|Workload group allocation by cap resource percent<p><p>Allocated percentage of resources relative to the specified cap resources per workload group. Applies only to data warehouses. |`wlg_allocation_relative_to_wlg_effective_cap_percent` |Percent |Maximum |WorkloadGroupName, IsUserDefined |Yes|
|Effective cap resource percent<p><p>A hard limit on the percentage of resources allowed for the workload group, taking into account Effective Min Resource Percentage allocated for other workload groups. Applies only to data warehouses. |`wlg_effective_cap_resource_percent` |Percent |Maximum |WorkloadGroupName, IsUserDefined |Yes|
|Effective min resource percent<p><p>Minimum percentage of resources reserved and isolated for the workload group, taking into account the service level minimum. Applies only to data warehouses. |`wlg_effective_min_resource_percent` |Percent |Maximum |WorkloadGroupName, IsUserDefined |Yes|
|Workload group queued queries<p><p>Queued queries within the workload group. Applies only to data warehouses. |`wlg_queued_queries` |Count |Total |WorkloadGroupName, IsUserDefined |Yes|
|Workers percentage<p><p>Workers percentage. Not applicable to data warehouses. |`workers_percent` |Percent |Average |No Dimensions |Yes|
|In-Memory OLTP storage percent<p><p>In-Memory OLTP storage percent. Not applicable to data warehouses. |`xtp_storage_percent` |Percent |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->