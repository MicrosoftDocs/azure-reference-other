---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DBforPostgreSQL/flexibleServers, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Active Connections**<p><p>Active Connections |`active_connections` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Analyze Counter User Tables**<p><p>Number of times user only tables have been manually analyzed in this database |`analyze_count_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**AutoAnalyze Counter User Tables**<p><p>Number of times user only tables have been analyzed by the autovacuum daemon in this database |`autoanalyze_count_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**AutoVacuum Counter User Tables**<p><p>Number of times user only tables have been vacuumed by the autovacuum daemon in this database |`autovacuum_count_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Backup Storage Used**<p><p>Backup Storage Used |`backup_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Disk Blocks Hit**<p><p>Number of times disk blocks were found already in the buffer cache, so that a read was not necessary |`blks_hit` |Count |Total |`DatabaseName`|PT1M |Yes|
|**Disk Blocks Read**<p><p>Number of disk blocks read in this database |`blks_read` |Count |Total |`DatabaseName`|PT1M |Yes|
|**Bloat Percent (Preview)**<p><p>Estimated bloat percentage for user only tables in this database |`bloat_percent` |Percent |Maximum |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Active client connections**<p><p>Connections from clients which are associated with a PostgreSQL connection |`client_connections_active` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|**Waiting client connections**<p><p>Connections from clients that are waiting for a PostgreSQL connection to service them |`client_connections_waiting` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|**Failed Connections**<p><p>Failed Connections |`connections_failed` |Count |Total |\<none\>|PT1M |Yes|
|**Succeeded Connections**<p><p>Succeeded Connections |`connections_succeeded` |Count |Total |\<none\>|PT1M |Yes|
|**CPU Credits Consumed**<p><p>Total number of credits consumed by the database server |`cpu_credits_consumed` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**CPU Credits Remaining**<p><p>Total number of credits available to burst |`cpu_credits_remaining` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**CPU percent**<p><p>CPU percent |`cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Deadlocks**<p><p>Number of deadlocks detected in this database |`deadlocks` |Count |Total |`DatabaseName`|PT1M |Yes|
|**Disk Bandwidth Consumed Percentage**<p><p>Percentage of disk bandwidth consumed per minute |`disk_bandwidth_consumed_percentage` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Disk IOPS Consumed Percentage**<p><p>Percentage of disk I/Os consumed per minute |`disk_iops_consumed_percentage` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Disk Queue Depth**<p><p>Number of outstanding I/O operations to the data disk |`disk_queue_depth` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**IOPS**<p><p>IO Operations per second |`iops` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Database Is Alive**<p><p>Indicates if the database is up or not |`is_db_alive` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Max Logical Replication Lag**<p><p>Maximum lag across all logical replication slots |`logical_replication_delay_in_bytes` |Bytes |Maximum, Minimum, Average |\<none\>|PT1M |Yes|
|**Oldest Query**<p><p>The age in seconds of the longest query that is currently running |`longest_query_time_sec` |Seconds |Maximum |\<none\>|PT1M |Yes|
|**Oldest Transaction**<p><p>The age in seconds of the longest transaction (including idle transactions) |`longest_transaction_time_sec` |Seconds |Maximum |\<none\>|PT1M |Yes|
|**Max Connections**<p><p>Max connections |`max_connections` |Count |Maximum |\<none\>|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Maximum Used Transaction IDs**<p><p>Maximum Used Transaction IDs |`maximum_used_transactionIDs` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Memory percent**<p><p>Memory percent |`memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Estimated Dead Rows User Tables**<p><p>Estimated number of dead rows for user only tables in this database |`n_dead_tup_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Estimated Live Rows User Tables**<p><p>Estimated number of live rows for user only tables in this database |`n_live_tup_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Estimated Modifications User Tables**<p><p>Estimated number of rows modified since user only tables were last analyzed |`n_mod_since_analyze_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Network Out**<p><p>Network Out across active connections |`network_bytes_egress` |Bytes |Total |\<none\>|PT1M |Yes|
|**Network In**<p><p>Network In across active connections |`network_bytes_ingress` |Bytes |Total |\<none\>|PT1M |Yes|
|**Number of connection pools**<p><p>Total number of connection pools |`num_pools` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|**Backends**<p><p>Number of backends connected to this database |`numbackends` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|**Oldest Backend**<p><p>The age in seconds of the oldest backend (irrespective of the state) |`oldest_backend_time_sec` |Seconds |Maximum |\<none\>|PT1M |Yes|
|**Oldest xmin**<p><p>The actual value of the oldest xmin. |`oldest_backend_xmin` |Count |Maximum |\<none\>|PT1M |Yes|
|**Oldest xmin Age**<p><p>Age in units of the oldest xmin. It indicated how many transactions passed since oldest xmin |`oldest_backend_xmin_age` |Count |Maximum |\<none\>|PT1M |Yes|
|**Max Physical Replication Lag**<p><p>Maximum lag across all asynchronous physical replication slots |`physical_replication_delay_in_bytes` |Bytes |Maximum, Minimum, Average |\<none\>|PT1M |Yes|
|**Read Replica Lag**<p><p>Read Replica lag in seconds |`physical_replication_delay_in_seconds` |Seconds |Maximum, Minimum, Average |\<none\>|PT1M |Yes|
|**Read IOPS**<p><p>Number of data disk I/O read operations per second |`read_iops` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Read Throughput Bytes/Sec**<p><p>Bytes read per second from the data disk during monitoring period |`read_throughput` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Active server connections**<p><p>Connections to PostgreSQL that are in use by a client connection |`server_connections_active` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|**Idle server connections**<p><p>Connections to PostgreSQL that are idle, ready to service a new client connection |`server_connections_idle` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|**Sessions by State**<p><p>Overall state of the backends |`sessions_by_state` |Count |Maximum, Minimum, Average |`State`|PT1M |Yes|
|**Sessions by WaitEventType**<p><p>Sessions by the type of event for which the backend is waiting |`sessions_by_wait_event_type` |Count |Maximum, Minimum, Average |`WaitEventType`|PT1M |Yes|
|**Storage Free**<p><p>Storage Free |`storage_free` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Storage percent**<p><p>Storage percent |`storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Storage used**<p><p>Storage used |`storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**User Tables Analyzed**<p><p>Number of user only tables that have been analyzed in this database |`tables_analyzed_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**User Tables AutoAnalyzed**<p><p>Number of user only tables that have been analyzed by the autovacuum daemon in this database |`tables_autoanalyzed_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**User Tables AutoVacuumed**<p><p>Number of user only tables that have been vacuumed by the autovacuum daemon in this database |`tables_autovacuumed_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**User Tables Counter**<p><p>Number of user only tables in this database |`tables_counter_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**User Tables Vacuumed**<p><p>Number of user only tables that have been vacuumed in this database |`tables_vacuumed_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Temporary Files Size**<p><p>Total amount of data written to temporary files by queries in this database |`temp_bytes` |Bytes |Total |`DatabaseName`|PT1M |Yes|
|**Temporary Files**<p><p>Number of temporary files created by queries in this database |`temp_files` |Count |Total |`DatabaseName`|PT1M |Yes|
|**Total pooled connections**<p><p>Current number of pooled connections |`total_pooled_connections` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|**Transactions per second (Preview)**<p><p>Number of transactions executed within a second |`tps` |Count |Minimum, Maximum, Total |`DatabaseName`|PT1M |Yes|
|**Tuples Deleted**<p><p>Number of rows deleted by queries in this database |`tup_deleted` |Count |Total |`DatabaseName`|PT1M |Yes|
|**Tuples Fetched**<p><p>Number of rows fetched by queries in this database |`tup_fetched` |Count |Total |`DatabaseName`|PT1M |Yes|
|**Tuples Inserted**<p><p>Number of rows inserted by queries in this database |`tup_inserted` |Count |Total |`DatabaseName`|PT1M |Yes|
|**Tuples Returned**<p><p>Number of rows returned by queries in this database |`tup_returned` |Count |Total |`DatabaseName`|PT1M |Yes|
|**Tuples Updated**<p><p>Number of rows updated by queries in this database |`tup_updated` |Count |Total |`DatabaseName`|PT1M |Yes|
|**Transaction Log Storage Used**<p><p>Transaction Log Storage Used |`txlogs_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Vacuum Counter User Tables**<p><p>Number of times user only tables have been manually vacuumed in this database (not counting VACUUM FULL) |`vacuum_count_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Write IOPS**<p><p>Number of data disk I/O write operations per second |`write_iops` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Write Throughput Bytes/Sec**<p><p>Bytes written per second to the data disk during monitoring period |`write_throughput` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Transactions Committed**<p><p>Number of transactions in this database that have been committed |`xact_commit` |Count |Total |`DatabaseName`|PT1M |Yes|
|**Transactions Rolled Back**<p><p>Number of transactions in this database that have been rolled back |`xact_rollback` |Count |Total |`DatabaseName`|PT1M |Yes|
|**Total Transactions**<p><p>Number of total transactions executed in this database |`xact_total` |Count |Total |`DatabaseName`|PT1M |Yes|