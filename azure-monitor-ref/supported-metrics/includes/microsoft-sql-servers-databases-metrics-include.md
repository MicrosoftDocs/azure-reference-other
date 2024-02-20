---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Sql/servers/databases, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Basic|**Active queries**<br><br>Active queries across all workload groups. Applies only to data warehouses. |`active_queries` |Count |Total |\<none\>|PT1M |Yes|
|Basic|**Data space allocated**<br><br>Allocated data storage. Not applicable to data warehouses. |`allocated_data_storage` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**App CPU billed**<br><br>App CPU billed. Applies to serverless databases. |`app_cpu_billed` |Count |Total |\<none\>|PT1M |Yes|
|Basic|**App CPU billed HA replicas**<br><br>Sum of app CPU billed across all HA replicas associated with the primary replica or a named replica. |`app_cpu_billed_ha_replicas` |Count |Total |\<none\>|PT1M |Yes|
|Basic|**App CPU percentage**<br><br>App CPU percentage. Applies to serverless databases. |`app_cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**App memory percentage**<br><br>App memory percentage. Applies to serverless databases. |`app_memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Data storage size**<br><br>Data storage size. Applies to Hyperscale databases. |`base_blob_size_bytes` |Bytes |Average, Maximum, Minimum |\<none\>|P1D |Yes|
|Basic|**Blocked by Firewall**<br><br>Blocked by Firewall |`blocked_by_firewall` |Count |Total, Count |\<none\>|PT1M |Yes|
|Basic|**Cache hit percentage**<br><br>Cache hit percentage. Applies only to data warehouses. |`cache_hit_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Cache used percentage**<br><br>Cache used percentage. Applies only to data warehouses. |`cache_used_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Failed Connections : System Errors**<br><br>Failed Connections |`connection_failed` |Count |Total, Count |`Error`, `ValidatedDriverNameAndVersion`|PT1M |Yes|
|Basic|**Failed Connections : User Errors**<br><br>Failed Connections : User Errors |`connection_failed_user_error` |Count |Total, Count |`Error`, `ValidatedDriverNameAndVersion`|PT1M |Yes|
|Basic|**Successful Connections**<br><br>Successful Connections |`connection_successful` |Count |Total, Count |`SslProtocol`, `ValidatedDriverNameAndVersion`|PT1M |Yes|
|Basic|**CPU limit**<br><br>CPU limit. Applies to vCore-based databases. |`cpu_limit` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**CPU percentage**<br><br>CPU percentage |`cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**CPU used**<br><br>CPU used. Applies to vCore-based databases. |`cpu_used` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Deadlocks**<br><br>Deadlocks. Not applicable to data warehouses. |`deadlock` |Count |Total, Count |\<none\>|PT1M |Yes|
|Basic|**Differential backup storage size**<br><br>Cumulative differential backup storage size. Applies to vCore-based databases. Not applicable to Hyperscale databases. |`diff_backup_size_bytes` |Bytes |Average, Maximum, Minimum |\<none\>|P1D |Yes|
|Basic|**DTU percentage**<br><br>DTU Percentage. Applies to DTU-based databases. |`dtu_consumption_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**DTU Limit**<br><br>DTU Limit. Applies to DTU-based databases. |`dtu_limit` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**DTU used**<br><br>DTU used. Applies to DTU-based databases. |`dtu_used` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**DWU percentage**<br><br>DWU percentage. Applies only to data warehouses. |`dwu_consumption_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**DWU limit**<br><br>DWU limit. Applies only to data warehouses. |`dwu_limit` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**DWU used**<br><br>DWU used. Applies only to data warehouses. |`dwu_used` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Free amount consumed**<br><br>Free amount of vCore seconds consumed this month. Applies only to free database offer. |`free_amount_consumed` |Count |Average, Maximum, Minimum |\<none\>|PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Basic|**Free amount remaining**<br><br>Free amount of vCore seconds remaining this month. Applies only to free database offer. |`free_amount_remaining` |Count |Average, Maximum, Minimum |\<none\>|PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Basic|**Full backup storage size**<br><br>Cumulative full backup storage size. Applies to vCore-based databases. Not applicable to Hyperscale databases. |`full_backup_size_bytes` |Bytes |Average, Maximum, Minimum |\<none\>|P1D |Yes|
|Basic|**Failed Ledger Digest Uploads**<br><br>Ledger digests that failed to be uploaded. |`ledger_digest_upload_failed` |Count |Count |\<none\>|PT1M |Yes|
|Basic|**Successful Ledger Digest Uploads**<br><br>Ledger digests that were successfully uploaded. |`ledger_digest_upload_success` |Count |Count |\<none\>|PT1M |Yes|
|Basic|**Local tempdb percentage**<br><br>Local tempdb percentage. Applies only to data warehouses. |`local_tempdb_usage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Basic|**Log backup storage size**<br><br>Cumulative log backup storage size. Applies to vCore-based and Hyperscale databases. |`log_backup_size_bytes` |Bytes |Average, Maximum, Minimum |\<none\>|P1D |Yes|
|Basic|**Log IO percentage**<br><br>Log IO percentage. Not applicable to data warehouses. |`log_write_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Memory percentage**<br><br>Memory percentage. Applies only to data warehouses. |`memory_usage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Data IO percentage**<br><br>Data IO percentage |`physical_data_read_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Queued queries**<br><br>Queued queries across all workload groups. Applies only to data warehouses. |`queued_queries` |Count |Total |\<none\>|PT1M |Yes|
|Basic|**Sessions count**<br><br>Number of active sessions. Not applicable to Synapse DW Analytics. |`sessions_count` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Sessions percentage**<br><br>Sessions percentage. Not applicable to data warehouses. |`sessions_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Data backup storage size**<br><br>Cumulative data backup storage size. Applies to Hyperscale databases. |`snapshot_backup_size_bytes` |Bytes |Average, Maximum, Minimum |\<none\>|P1D |Yes|
|InstanceAndAppAdvanced|**SQL instance CPU percent**<br><br>CPU usage by all user and system workloads. Not applicable to data warehouses. |`sql_instance_cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|InstanceAndAppAdvanced|**SQL instance memory percent**<br><br>Memory usage by the database engine instance. Not applicable to data warehouses. |`sql_instance_memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|InstanceAndAppAdvanced|**SQL Server process core percent**<br><br>CPU usage as a percentage of the SQL DB process. Not applicable to data warehouses. (This metric is equivalent to sql_instance_cpu_percent, and will be removed in the future.) |`sqlserver_process_core_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|InstanceAndAppAdvanced|**SQL Server process memory percent**<br><br>Memory usage as a percentage of the SQL DB process. Not applicable to data warehouses. (This metric is equivalent to sql_instance_memory_percent, and will be removed in the future.) |`sqlserver_process_memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Data space used**<br><br>Data space used. Not applicable to data warehouses. |`storage` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Data space used percent**<br><br>Data space used percent. Not applicable to data warehouses or hyperscale databases. |`storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|InstanceAndAppAdvanced|**Tempdb Data File Size Kilobytes**<br><br>Space used in tempdb data files in kilobytes. Not applicable to data warehouses. |`tempdb_data_size` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|InstanceAndAppAdvanced|**Tempdb Log File Size Kilobytes**<br><br>Space used in tempdb transaction log file in kilobytes. Not applicable to data warehouses. |`tempdb_log_size` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|InstanceAndAppAdvanced|**Tempdb Percent Log Used**<br><br>Space used percentage in tempdb transaction log file. Not applicable to data warehouses. |`tempdb_log_used_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|WorkloadManagement|**Workload group active queries**<br><br>Active queries within the workload group. Applies only to data warehouses. |`wlg_active_queries` |Count |Total |`WorkloadGroupName`, `IsUserDefined`|PT1M |Yes|
|WorkloadManagement|**Workload group query timeouts**<br><br>Queries that have timed out for the workload group. Applies only to data warehouses. |`wlg_active_queries_timeouts` |Count |Total |`WorkloadGroupName`, `IsUserDefined`|PT1M |Yes|
|WorkloadManagement|**Workload group allocation by system percent**<br><br>Allocated percentage of resources relative to the entire system per workload group. Applies only to data warehouses. |`wlg_allocation_relative_to_system_percent` |Percent |Average, Maximum, Minimum, Total |`WorkloadGroupName`, `IsUserDefined`|PT1M |Yes|
|WorkloadManagement|**Workload group allocation by cap resource percent**<br><br>Allocated percentage of resources relative to the specified cap resources per workload group. Applies only to data warehouses. |`wlg_allocation_relative_to_wlg_effective_cap_percent` |Percent |Average, Maximum, Minimum |`WorkloadGroupName`, `IsUserDefined`|PT1M |Yes|
|WorkloadManagement|**Effective cap resource percent**<br><br>A hard limit on the percentage of resources allowed for the workload group, taking into account Effective Min Resource Percentage allocated for other workload groups. Applies only to data warehouses. |`wlg_effective_cap_resource_percent` |Percent |Average, Maximum, Minimum |`WorkloadGroupName`, `IsUserDefined`|PT1M |Yes|
|WorkloadManagement|**Effective min resource percent**<br><br>Minimum percentage of resources reserved and isolated for the workload group, taking into account the service level minimum. Applies only to data warehouses. |`wlg_effective_min_resource_percent` |Percent |Average, Maximum, Minimum, Total |`WorkloadGroupName`, `IsUserDefined`|PT1M |Yes|
|WorkloadManagement|**Workload group queued queries**<br><br>Queued queries within the workload group. Applies only to data warehouses. |`wlg_queued_queries` |Count |Total |`WorkloadGroupName`, `IsUserDefined`|PT1M |Yes|
|Basic|**Workers percentage**<br><br>Workers percentage. Not applicable to data warehouses. |`workers_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**In-Memory OLTP storage percent**<br><br>In-Memory OLTP storage percent. Not applicable to data warehouses. |`xtp_storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|