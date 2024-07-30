---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.DBforPostgreSQL/flexibleServers, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Active Connections**<br><br>Active Connections |`active_connections` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Autovacuum|**Analyze Counter User Tables**<br><br>Number of times user only tables have been manually analyzed in this database |`analyze_count_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Autovacuum|**AutoAnalyze Counter User Tables**<br><br>Number of times user only tables have been analyzed by the autovacuum daemon in this database |`autoanalyze_count_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Autovacuum|**AutoVacuum Counter User Tables**<br><br>Number of times user only tables have been vacuumed by the autovacuum daemon in this database |`autovacuum_count_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Saturation|**Backup Storage Used**<br><br>Backup Storage Used |`backup_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Database|**Disk Blocks Hit**<br><br>Number of times disk blocks were found already in the buffer cache, so that a read was not necessary |`blks_hit` |Count |Total |`DatabaseName`|PT1M |Yes|
|Database|**Disk Blocks Read**<br><br>Number of disk blocks read in this database |`blks_read` |Count |Total |`DatabaseName`|PT1M |Yes|
|Autovacuum|**Bloat Percent (Preview)**<br><br>Estimated bloat percentage for user only tables in this database |`bloat_percent` |Percent |Maximum |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|PgBouncer metrics|**Active client connections**<br><br>Connections from clients which are associated with a PostgreSQL connection |`client_connections_active` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|PgBouncer metrics|**Waiting client connections**<br><br>Connections from clients that are waiting for a PostgreSQL connection to service them |`client_connections_waiting` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|Errors|**Failed Connections**<br><br>Failed Connections |`connections_failed` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Succeeded Connections**<br><br>Succeeded Connections |`connections_succeeded` |Count |Total |\<none\>|PT1M |Yes|
|Saturation|**CPU Credits Consumed**<br><br>Total number of credits consumed by the database server |`cpu_credits_consumed` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**CPU Credits Remaining**<br><br>Total number of credits available to burst |`cpu_credits_remaining` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**CPU percent**<br><br>CPU percent |`cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Database|**Database Size**<br><br>Total database size |`database_size_bytes` |Bytes |Average, Maximum, Minimum |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Database|**Deadlocks**<br><br>Number of deadlocks detected in this database |`deadlocks` |Count |Total |`DatabaseName`|PT1M |Yes|
|Saturation|**Disk Bandwidth Consumed Percentage**<br><br>Percentage of disk bandwidth consumed per minute |`disk_bandwidth_consumed_percentage` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Disk IOPS Consumed Percentage**<br><br>Percentage of disk I/Os consumed per minute |`disk_iops_consumed_percentage` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Disk Queue Depth**<br><br>Number of outstanding I/O operations to the data disk |`disk_queue_depth` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**IOPS**<br><br>IO Operations per second |`iops` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Availability|**Database Is Alive**<br><br>Indicates if the database is up or not |`is_db_alive` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Logical Replication|**Max Logical Replication Lag**<br><br>Maximum lag across all logical replication slots |`logical_replication_delay_in_bytes` |Bytes |Maximum, Minimum, Average |\<none\>|PT1M |Yes|
|Activity|**Oldest Query**<br><br>The age in seconds of the longest query that is currently running |`longest_query_time_sec` |Seconds |Maximum |\<none\>|PT1M |Yes|
|Activity|**Oldest Transaction**<br><br>The age in seconds of the longest transaction (including idle transactions) |`longest_transaction_time_sec` |Seconds |Maximum |\<none\>|PT1M |Yes|
|Traffic|**Max Connections**<br><br>Max connections |`max_connections` |Count |Maximum |\<none\>|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Maximum Used Transaction IDs**<br><br>Maximum Used Transaction IDs |`maximum_used_transactionIDs` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Memory percent**<br><br>Memory percent |`memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Autovacuum|**Estimated Dead Rows User Tables**<br><br>Estimated number of dead rows for user only tables in this database |`n_dead_tup_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Autovacuum|**Estimated Live Rows User Tables**<br><br>Estimated number of live rows for user only tables in this database |`n_live_tup_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Autovacuum|**Estimated Modifications User Tables**<br><br>Estimated number of rows modified since user only tables were last analyzed |`n_mod_since_analyze_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Network Out**<br><br>Network Out across active connections |`network_bytes_egress` |Bytes |Total |\<none\>|PT1M |Yes|
|Traffic|**Network In**<br><br>Network In across active connections |`network_bytes_ingress` |Bytes |Total |\<none\>|PT1M |Yes|
|PgBouncer metrics|**Number of connection pools**<br><br>Total number of connection pools |`num_pools` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|Database|**Backends**<br><br>Number of backends connected to this database |`numbackends` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|Activity|**Oldest Backend**<br><br>The age in seconds of the oldest backend (irrespective of the state) |`oldest_backend_time_sec` |Seconds |Maximum |\<none\>|PT1M |Yes|
|Activity|**Oldest xmin**<br><br>The actual value of the oldest xmin. |`oldest_backend_xmin` |Count |Maximum |\<none\>|PT1M |Yes|
|Activity|**Oldest xmin Age**<br><br>Age in units of the oldest xmin. It indicated how many transactions passed since oldest xmin |`oldest_backend_xmin_age` |Count |Maximum |\<none\>|PT1M |Yes|
|Replication|**Max Physical Replication Lag**<br><br>Maximum lag across all asynchronous physical replication slots |`physical_replication_delay_in_bytes` |Bytes |Maximum, Minimum, Average |\<none\>|PT1M |Yes|
|Replication|**Read Replica Lag**<br><br>Read Replica lag in seconds |`physical_replication_delay_in_seconds` |Seconds |Maximum, Minimum, Average |\<none\>|PT1M |Yes|
|Saturation|**CPU percent from platform (Preview)**<br><br>CPU percent from platform |`platform_cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Read IOPS**<br><br>Number of data disk I/O read operations per second |`read_iops` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Read Throughput Bytes/Sec**<br><br>Bytes read per second from the data disk during monitoring period |`read_throughput` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|PgBouncer metrics|**Active server connections**<br><br>Connections to PostgreSQL that are in use by a client connection |`server_connections_active` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|PgBouncer metrics|**Idle server connections**<br><br>Connections to PostgreSQL that are idle, ready to service a new client connection |`server_connections_idle` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|Activity|**Sessions by State**<br><br>Overall state of the backends |`sessions_by_state` |Count |Maximum, Minimum, Average |`State`|PT1M |Yes|
|Activity|**Sessions by WaitEventType**<br><br>Sessions by the type of event for which the backend is waiting |`sessions_by_wait_event_type` |Count |Maximum, Minimum, Average |`WaitEventType`|PT1M |Yes|
|Saturation|**Storage Free**<br><br>Storage Free |`storage_free` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Storage percent**<br><br>Storage percent |`storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Storage used**<br><br>Storage used |`storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Autovacuum|**User Tables Analyzed**<br><br>Number of user only tables that have been analyzed in this database |`tables_analyzed_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Autovacuum|**User Tables AutoAnalyzed**<br><br>Number of user only tables that have been analyzed by the autovacuum daemon in this database |`tables_autoanalyzed_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Autovacuum|**User Tables AutoVacuumed**<br><br>Number of user only tables that have been vacuumed by the autovacuum daemon in this database |`tables_autovacuumed_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Autovacuum|**User Tables Counter**<br><br>Number of user only tables in this database |`tables_counter_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Autovacuum|**User Tables Vacuumed**<br><br>Number of user only tables that have been vacuumed in this database |`tables_vacuumed_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Database|**Temporary Files Size**<br><br>Total amount of data written to temporary files by queries in this database |`temp_bytes` |Bytes |Total |`DatabaseName`|PT1M |Yes|
|Database|**Temporary Files**<br><br>Number of temporary files created by queries in this database |`temp_files` |Count |Total |`DatabaseName`|PT1M |Yes|
|PgBouncer metrics|**Total pooled connections**<br><br>Current number of pooled connections |`total_pooled_connections` |Count |Maximum, Minimum, Average |`DatabaseName`|PT1M |Yes|
|Database|**Transactions per second (Preview)**<br><br>Number of transactions executed within a second |`tps` |Count |Minimum, Maximum, Total |`DatabaseName`|PT1M |Yes|
|Database|**Tuples Deleted**<br><br>Number of rows deleted by queries in this database |`tup_deleted` |Count |Total |`DatabaseName`|PT1M |Yes|
|Database|**Tuples Fetched**<br><br>Number of rows fetched by queries in this database |`tup_fetched` |Count |Total |`DatabaseName`|PT1M |Yes|
|Database|**Tuples Inserted**<br><br>Number of rows inserted by queries in this database |`tup_inserted` |Count |Total |`DatabaseName`|PT1M |Yes|
|Database|**Tuples Returned**<br><br>Number of rows returned by queries in this database |`tup_returned` |Count |Total |`DatabaseName`|PT1M |Yes|
|Database|**Tuples Updated**<br><br>Number of rows updated by queries in this database |`tup_updated` |Count |Total |`DatabaseName`|PT1M |Yes|
|Saturation|**Transaction Log Storage Used**<br><br>Transaction Log Storage Used |`txlogs_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Autovacuum|**Vacuum Counter User Tables**<br><br>Number of times user only tables have been manually vacuumed in this database (not counting VACUUM FULL) |`vacuum_count_user_tables` |Count |Maximum, Minimum, Average |`DatabaseName`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Saturation|**Write IOPS**<br><br>Number of data disk I/O write operations per second |`write_iops` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Write Throughput Bytes/Sec**<br><br>Bytes written per second to the data disk during monitoring period |`write_throughput` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Database|**Transactions Committed**<br><br>Number of transactions in this database that have been committed |`xact_commit` |Count |Total |`DatabaseName`|PT1M |Yes|
|Database|**Transactions Rolled Back**<br><br>Number of transactions in this database that have been rolled back |`xact_rollback` |Count |Total |`DatabaseName`|PT1M |Yes|
|Database|**Total Transactions**<br><br>Number of total transactions executed in this database |`xact_total` |Count |Total |`DatabaseName`|PT1M |Yes|