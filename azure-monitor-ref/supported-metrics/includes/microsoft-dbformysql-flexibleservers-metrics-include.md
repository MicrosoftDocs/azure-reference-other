---
ms.service: azure-monitor
ms.topic: include
ms.date: 05/06/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DBforMySQL/flexibleServers, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Errors|**Aborted Connections**<br><br>Aborted Connections |`aborted_connections` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Active Connections**<br><br>Active Connections |`active_connections` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Active Transactions**<br><br>Number of active transactions. |`active_transactions` |Count |Total, Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Available Memory Bytes (deprecated)**<br><br>Amount of physical memory, in bytes. Deprecated, Please check memory_percent for the memory usage. |`available_memory_bytes` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Backup Storage Used**<br><br>Backup Storage Used |`backup_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Saturation|**Binlog Storage Used**<br><br>Storage used by Binlog files. |`binlog_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Com Alter Table**<br><br>The number of times ALTER TABLE statement has been executed. |`Com_alter_table` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Create DB**<br><br>The number of times CREATE DB statement has been executed. |`Com_create_db` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Create Table**<br><br>The number of times CREATE TABLE statement has been executed. |`Com_create_table` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Delete**<br><br>The number of times DELETE statement has been executed. |`Com_delete` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Drop DB**<br><br>The number of times DROP DB statement has been executed. |`Com_drop_db` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Drop Table**<br><br>The number of times DROP TABLE statement has been executed. |`Com_drop_table` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Insert**<br><br>The number of times INSERT statement has been executed. |`Com_insert` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Select**<br><br>The number of times SELECT statement has been executed. |`Com_select` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Com Update**<br><br>The number of times UPDATE statement has been executed. |`Com_update` |Count |Total |\<none\>|PT1M |Yes|
|Saturation|**CPU Credits Consumed**<br><br>CPU Credits Consumed |`cpu_credits_consumed` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**CPU Credits Remaining**<br><br>CPU Credits Remaining |`cpu_credits_remaining` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Host CPU Percent**<br><br>Host CPU Percent |`cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Data Storage Used**<br><br>Storage used by data files. |`data_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Availability|**HA IO Status**<br><br>Status for replication IO thread running  |`HA_IO_status` |Count |Maximum |\<none\>|PT1M |Yes|
|Latency|**HA Replication Lag**<br><br>HA Replication lag in seconds |`HA_replication_lag` |Seconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Availability|**HA SQL Status**<br><br>Status for replication SQL thread running  |`HA_SQL_status` |Count |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Ibdata1 Storage Used**<br><br>Storage used by ibdata1 files. |`ibdata1_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**InnoDB Buffer Pool Pages Data**<br><br>The number of pages in the InnoDB buffer pool containing data. |`Innodb_buffer_pool_pages_data` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**InnoDB Buffer Pool Pages Dirty**<br><br>The current number of dirty pages in the InnoDB buffer pool. |`Innodb_buffer_pool_pages_dirty` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Innodb Buffer Pool Pages Flushed**<br><br>The number of requests to flush pages from the InnoDB buffer pool. |`Innodb_buffer_pool_pages_flushed` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**InnoDB Buffer Pool Pages Free**<br><br>The number of free pages in the InnoDB buffer pool. |`Innodb_buffer_pool_pages_free` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**InnoDB Buffer Pool Read Requests**<br><br>The number of logical read requests. |`Innodb_buffer_pool_read_requests` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**InnoDB Buffer Pool Reads**<br><br>The number of logical reads that InnoDB could not satisfy from the buffer pool, and had to read directly from disk. |`Innodb_buffer_pool_reads` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Innodb Data Writes**<br><br>The total number of data writes. |`Innodb_data_writes` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Latency|**Innodb Row Lock Time**<br><br>The total time spent in acquiring row locks for InnoDB tables, in milliseconds. |`Innodb_row_lock_time` |Milliseconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Latency|**Innodb Row Lock Waits**<br><br>The number of times operations on InnoDB tables had to wait for a row lock. |`Innodb_row_lock_waits` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Storage IO Percent**<br><br>Storage I/O consumption percent |`io_consumption_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**MySQL Lock Deadlocks**<br><br>Number of deadlocks. |`lock_deadlocks` |Count |Total, Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**MySQL Lock Row Lock Waits**<br><br>Number of times a row lock had to be waited for (innodb_row_lock_waits). |`lock_row_lock_waits` |Count |Total, Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**MySQL Lock Timeouts**<br><br>Number of lock timeouts. |`lock_timeouts` |Count |Total, Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Memory Percent**<br><br>Memory Percent |`memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Host Network Out**<br><br>Host Network egress in bytes |`network_bytes_egress` |Bytes |Total |\<none\>|PT1M |Yes|
|Traffic|**Host Network In**<br><br>Host Network ingress in bytes |`network_bytes_ingress` |Bytes |Total |\<none\>|PT1M |Yes|
|Saturation|**Others Storage Used**<br><br>Storage used by other files. |`others_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Queries**<br><br>Queries |`Queries` |Count |Total |\<none\>|PT1M |Yes|
|Availability|**Replica IO Status**<br><br>Status for replication IO thread running  |`Replica_IO_Running` |Count |Maximum |\<none\>|PT1M |No|
|Availability|**Replica SQL Status**<br><br>Status for replication SQL thread running  |`Replica_SQL_Running` |Count |Maximum |\<none\>|PT1M |No|
|Latency|**Replication Lag In Seconds**<br><br>Replication lag in seconds |`replication_lag` |Seconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Serverlog Storage Limit**<br><br>Serverlog Storage Limit |`serverlog_storage_limit` |Bytes |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Serverlog Storage Percent**<br><br>Serverlog Storage Percent |`serverlog_storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Serverlog Storage Used**<br><br>Serverlog Storage Used |`serverlog_storage_usage` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Slow Queries**<br><br>The number of queries that have taken more than long_query_time seconds. |`Slow_queries` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Storage IO Count**<br><br>The number of storage I/O consumed. |`storage_io_count` |Count |Total |\<none\>|PT1M |No|
|Saturation|**Storage Limit**<br><br>Storage Limit |`storage_limit` |Bytes |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Storage Percent**<br><br>Storage Percent |`storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Storage Throttle Count (deprecated)**<br><br>Storage IO requests throttled in the selected time range. Deprecated, please check Storage IO Percent for throttling. |`storage_throttle_count` |Count |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Storage Used**<br><br>Storage Used |`storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Threads Running**<br><br>The number of threads that are not sleeping. |`Threads_running` |Count |Total, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Total Connections**<br><br>Total Connections |`total_connections` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**MySQL History List Length**<br><br>Length of the TRX_RSEG_HISTORY list. |`trx_rseg_history_len` |Count |Total, Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Latency|**MySQL Uptime**<br><br>The number of seconds that the server has been up. |`Uptime` |Seconds |Total, Maximum |\<none\>|PT1M |Yes|