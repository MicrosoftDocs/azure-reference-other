---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DBforMySQL/flexibleServers, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Errors|**Aborted Connections**<p><p>Aborted Connections |`aborted_connections` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Active Connections**<p><p>Active Connections |`active_connections` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Available Memory Bytes**<p><p>Amount of physical memory, in bytes. |`available_memory_bytes` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Backup Storage Used**<p><p>Backup Storage Used |`backup_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Saturation|**Binlog Storage Used**<p><p>Storage used by Binlog files. |`binlog_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Com Alter Table**<p><p>The number of times ALTER TABLE statement has been executed. |`Com_alter_table` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Create DB**<p><p>The number of times CREATE DB statement has been executed. |`Com_create_db` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Create Table**<p><p>The number of times CREATE TABLE statement has been executed. |`Com_create_table` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Delete**<p><p>The number of times DELETE statement has been executed. |`Com_delete` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Drop DB**<p><p>The number of times DROP DB statement has been executed. |`Com_drop_db` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Drop Table**<p><p>The number of times DROP TABLE statement has been executed. |`Com_drop_table` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Insert**<p><p>The number of times INSERT statement has been executed. |`Com_insert` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Select**<p><p>The number of times SELECT statement has been executed. |`Com_select` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Update**<p><p>The number of times UPDATE statement has been executed. |`Com_update` |Count |Total |\<none\>|PT1M |Yes|
|Saturation|**CPU Credits Consumed**<p><p>CPU Credits Consumed |`cpu_credits_consumed` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**CPU Credits Remaining**<p><p>CPU Credits Remaining |`cpu_credits_remaining` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Host CPU Percent**<p><p>Host CPU Percent |`cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Data Storage Used**<p><p>Storage used by data files. |`data_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Availability|**HA IO Status**<p><p>Status for replication IO thread running  |`HA_IO_status` |Count |Maximum |\<none\>|PT1M |Yes|
|Latency|**HA Replication Lag**<p><p>HA Replication lag in seconds |`HA_replication_lag` |Seconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Availability|**HA SQL Status**<p><p>Status for replication SQL thread running  |`HA_SQL_status` |Count |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Ibdata1 Storage Used**<p><p>Storage used by ibdata1 files. |`ibdata1_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**InnoDB Buffer Pool Pages Data**<p><p>The number of pages in the InnoDB buffer pool containing data. |`Innodb_buffer_pool_pages_data` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**InnoDB Buffer Pool Pages Dirty**<p><p>The current number of dirty pages in the InnoDB buffer pool. |`Innodb_buffer_pool_pages_dirty` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Innodb Buffer Pool Pages Flushed**<p><p>The number of requests to flush pages from the InnoDB buffer pool. |`Innodb_buffer_pool_pages_flushed` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**InnoDB Buffer Pool Pages Free**<p><p>The number of free pages in the InnoDB buffer pool. |`Innodb_buffer_pool_pages_free` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**InnoDB Buffer Pool Read Requests**<p><p>The number of logical read requests. |`Innodb_buffer_pool_read_requests` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**InnoDB Buffer Pool Reads**<p><p>The number of logical reads that InnoDB could not satisfy from the buffer pool, and had to read directly from disk. |`Innodb_buffer_pool_reads` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Innodb Data Writes**<p><p>The total number of data writes. |`Innodb_data_writes` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Latency|**Innodb Row Lock Time**<p><p>The total time spent in acquiring row locks for InnoDB tables, in milliseconds. |`Innodb_row_lock_time` |Milliseconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Latency|**Innodb Row Lock Waits**<p><p>The number of times operations on InnoDB tables had to wait for a row lock. |`Innodb_row_lock_waits` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Storage IO Percent**<p><p>Storage I/O consumption percent |`io_consumption_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Host Memory Percent**<p><p>Host Memory Percent |`memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Host Network Out**<p><p>Host Network egress in bytes |`network_bytes_egress` |Bytes |Total |\<none\>|PT1M |Yes|
|Traffic|**Host Network In**<p><p>Host Network ingress in bytes |`network_bytes_ingress` |Bytes |Total |\<none\>|PT1M |Yes|
|Saturation|**Others Storage Used**<p><p>Storage used by other files. |`others_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Queries**<p><p>Queries |`Queries` |Count |Total |\<none\>|PT1M |Yes|
|Availability|**Replica IO Status**<p><p>Status for replication IO thread running  |`Replica_IO_Running` |Count |Maximum |\<none\>|PT1M |No|
|Availability|**Replica SQL Status**<p><p>Status for replication SQL thread running  |`Replica_SQL_Running` |Count |Maximum |\<none\>|PT1M |No|
|Latency|**Replication Lag In Seconds**<p><p>Replication lag in seconds |`replication_lag` |Seconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Serverlog Storage Limit**<p><p>Serverlog Storage Limit |`serverlog_storage_limit` |Bytes |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Serverlog Storage Percent**<p><p>Serverlog Storage Percent |`serverlog_storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Serverlog Storage Used**<p><p>Serverlog Storage Used |`serverlog_storage_usage` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Slow Queries**<p><p>The number of queries that have taken more than long_query_time seconds. |`Slow_queries` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Storage IO Count**<p><p>The number of storage I/O consumed. |`storage_io_count` |Count |Total |\<none\>|PT1M |No|
|Saturation|**Storage Limit**<p><p>Storage Limit |`storage_limit` |Bytes |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Storage Percent**<p><p>Storage Percent |`storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Storage Throttle Count (deprecated)**<p><p>Storage IO requests throttled in the selected time range. Deprecated, please check Storage IO Percent for throttling. |`storage_throttle_count` |Count |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Storage Used**<p><p>Storage Used |`storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Threads Running**<p><p>The number of threads that are not sleeping. |`Threads_running` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Total Connections**<p><p>Total Connections |`total_connections` |Count |Total |\<none\>|PT1M |Yes|