---
title: Supported metrics - Microsoft.DBforMySQL/flexibleServers
description: Reference for Microsoft.DBforMySQL/flexibleServers metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.DBforMySQL/flexibleServers  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.DBforMySQL/flexibleServers resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Aborted Connections<p><p>Aborted Connections |`aborted_connections` |Count |Total |No Dimensions |Yes|
|Active Connections<p><p>Active Connections |`active_connections` |Count |Maximum |No Dimensions |Yes|
|Available Memory Bytes<p><p>Amount of physical memory, in bytes. |`available_memory_bytes` |Bytes |Average |No Dimensions |Yes|
|Backup Storage Used<p><p>Backup Storage Used |`backup_storage_used` |Bytes |Maximum |No Dimensions |Yes|
|Com Alter Table<p><p>The number of times ALTER TABLE statement has been executed. |`Com_alter_table` |Count |Total |No Dimensions |Yes|
|Com Create DB<p><p>The number of times CREATE DB statement has been executed. |`Com_create_db` |Count |Total |No Dimensions |Yes|
|Com Create Table<p><p>The number of times CREATE TABLE statement has been executed. |`Com_create_table` |Count |Total |No Dimensions |Yes|
|Com Delete<p><p>The number of times DELETE statement has been executed. |`Com_delete` |Count |Total |No Dimensions |Yes|
|Com Drop DB<p><p>The number of times DROP DB statement has been executed. |`Com_drop_db` |Count |Total |No Dimensions |Yes|
|Com Drop Table<p><p>The number of times DROP TABLE statement has been executed. |`Com_drop_table` |Count |Total |No Dimensions |Yes|
|Com Insert<p><p>The number of times INSERT statement has been executed. |`Com_insert` |Count |Total |No Dimensions |Yes|
|Com Select<p><p>The number of times SELECT statement has been executed. |`Com_select` |Count |Total |No Dimensions |Yes|
|Com Update<p><p>The number of times UPDATE statement has been executed. |`Com_update` |Count |Total |No Dimensions |Yes|
|CPU Credits Consumed<p><p>CPU Credits Consumed |`cpu_credits_consumed` |Count |Maximum |No Dimensions |Yes|
|CPU Credits Remaining<p><p>CPU Credits Remaining |`cpu_credits_remaining` |Count |Maximum |No Dimensions |Yes|
|Host CPU Percent<p><p>Host CPU Percent |`cpu_percent` |Percent |Maximum |No Dimensions |Yes|
|HA IO Status<p><p>Status for replication IO thread running  |`HA_IO_status` |Count |Maximum |No Dimensions |Yes|
|HA Replication Lag<p><p>HA Replication lag in seconds |`HA_replication_lag` |Seconds |Maximum |No Dimensions |Yes|
|HA SQL Status<p><p>Status for replication SQL thread running  |`HA_SQL_status` |Count |Maximum |No Dimensions |Yes|
|InnoDB Buffer Pool Pages Data<p><p>The number of pages in the InnoDB buffer pool containing data. |`Innodb_buffer_pool_pages_data` |Count |Total |No Dimensions |Yes|
|InnoDB Buffer Pool Pages Dirty<p><p>The current number of dirty pages in the InnoDB buffer pool. |`Innodb_buffer_pool_pages_dirty` |Count |Total |No Dimensions |Yes|
|InnoDB Buffer Pool Pages Free<p><p>The number of free pages in the InnoDB buffer pool. |`Innodb_buffer_pool_pages_free` |Count |Total |No Dimensions |Yes|
|InnoDB Buffer Pool Read Requests<p><p>The number of logical read requests. |`Innodb_buffer_pool_read_requests` |Count |Total |No Dimensions |Yes|
|InnoDB Buffer Pool Reads<p><p>The number of logical reads that InnoDB could not satisfy from the buffer pool, and had to read directly from disk. |`Innodb_buffer_pool_reads` |Count |Total |No Dimensions |Yes|
|Innodb Data Writes<p><p>The total number of data writes. |`Innodb_data_writes` |Count |Total |No Dimensions |Yes|
|Innodb Row Lock Time<p><p>The total time spent in acquiring row locks for InnoDB tables, in milliseconds. |`Innodb_row_lock_time` |Milliseconds |Average |No Dimensions |Yes|
|Storage IO Percent<p><p>Storage I/O consumption percent |`io_consumption_percent` |Percent |Maximum |No Dimensions |Yes|
|Host Memory Percent<p><p>Host Memory Percent |`memory_percent` |Percent |Maximum |No Dimensions |Yes|
|Host Network Out<p><p>Host Network egress in bytes |`network_bytes_egress` |Bytes |Total |No Dimensions |Yes|
|Host Network In<p><p>Host Network ingress in bytes |`network_bytes_ingress` |Bytes |Total |No Dimensions |Yes|
|Queries<p><p>Queries |`Queries` |Count |Total |No Dimensions |Yes|
|Replica IO Status<p><p>Status for replication IO thread running  |`Replica_IO_Running` |Count |Maximum |No Dimensions |No|
|Replica SQL Status<p><p>Status for replication SQL thread running  |`Replica_SQL_Running` |Count |Maximum |No Dimensions |No|
|Replication Lag In Seconds<p><p>Replication lag in seconds |`replication_lag` |Seconds |Maximum |No Dimensions |Yes|
|Serverlog Storage Limit<p><p>Serverlog Storage Limit |`serverlog_storage_limit` |Bytes |Maximum |No Dimensions |Yes|
|Serverlog Storage Percent<p><p>Serverlog Storage Percent |`serverlog_storage_percent` |Percent |Maximum |No Dimensions |Yes|
|Serverlog Storage Used<p><p>Serverlog Storage Used |`serverlog_storage_usage` |Bytes |Maximum |No Dimensions |Yes|
|Slow Queries<p><p>The number of queries that have taken more than long_query_time seconds. |`Slow_queries` |Count |Total |No Dimensions |Yes|
|Storage IO Count<p><p>The number of storage I/O consumed. |`storage_io_count` |Count |Total |No Dimensions |No|
|Storage Limit<p><p>Storage Limit |`storage_limit` |Bytes |Maximum |No Dimensions |Yes|
|Storage Percent<p><p>Storage Percent |`storage_percent` |Percent |Maximum |No Dimensions |Yes|
|Storage Throttle Count (deprecated)<p><p>Storage IO requests throttled in the selected time range. Deprecated, please check Storage IO Percent for throttling. |`storage_throttle_count` |Count |Maximum |No Dimensions |Yes|
|Storage Used<p><p>Storage Used |`storage_used` |Bytes |Maximum |No Dimensions |Yes|
|Threads Running<p><p>The number of threads that are not sleeping. |`Threads_running` |Count |Total |No Dimensions |Yes|
|Total Connections<p><p>Total Connections |`total_connections` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->