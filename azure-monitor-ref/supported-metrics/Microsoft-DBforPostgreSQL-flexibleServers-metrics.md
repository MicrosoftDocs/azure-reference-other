---
title: Supported metrics - Microsoft.DBforPostgreSQL/flexibleServers
description: Reference for Microsoft.DBforPostgreSQL/flexibleServers metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 09/04/2023
---
# Supported metrics for Microsoft.DBforPostgreSQL/flexibleServers  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.DBforPostgreSQL/flexibleServers resource type.

  

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
|Analyze Counter User Tables<p><p>Number of times user only tables have been manually analyzed in this database |`analyze_count_user_tables` |Count |Maximum |DatabaseName |Yes|
|AutoAnalyze Counter User Tables<p><p>Number of times user only tables have been analyzed by the autovacuum daemon in this database |`autoanalyze_count_user_tables` |Count |Maximum |DatabaseName |Yes|
|AutoVacuum Counter User Tables<p><p>Number of times user only tables have been vacuumed by the autovacuum daemon in this database |`autovacuum_count_user_tables` |Count |Maximum |DatabaseName |Yes|
|Backup Storage Used<p><p>Backup Storage Used |`backup_storage_used` |Bytes |Average |No Dimensions |Yes|
|Disk Blocks Hit<p><p>Number of times disk blocks were found already in the buffer cache, so that a read was not necessary |`blks_hit` |Count |Total |DatabaseName |Yes|
|Disk Blocks Read<p><p>Number of disk blocks read in this database |`blks_read` |Count |Total |DatabaseName |Yes|
|Bloat Percent (Preview)<p><p>Estimated bloat percentage for user only tables in this database |`bloat_percent` |Percent |Maximum |DatabaseName |Yes|
|Active client connections<p><p>Connections from clients which are associated with a PostgreSQL connection |`client_connections_active` |Count |Maximum |DatabaseName |Yes|
|Waiting client connections<p><p>Connections from clients that are waiting for a PostgreSQL connection to service them |`client_connections_waiting` |Count |Maximum |DatabaseName |Yes|
|Failed Connections<p><p>Failed Connections |`connections_failed` |Count |Total |No Dimensions |Yes|
|Succeeded Connections<p><p>Succeeded Connections |`connections_succeeded` |Count |Total |No Dimensions |Yes|
|CPU Credits Consumed<p><p>Total number of credits consumed by the database server |`cpu_credits_consumed` |Count |Average |No Dimensions |Yes|
|CPU Credits Remaining<p><p>Total number of credits available to burst |`cpu_credits_remaining` |Count |Average |No Dimensions |Yes|
|CPU percent<p><p>CPU percent |`cpu_percent` |Percent |Average |No Dimensions |Yes|
|Deadlocks<p><p>Number of deadlocks detected in this database |`deadlocks` |Count |Total |DatabaseName |Yes|
|Disk Bandwidth Consumed Percentage<p><p>Percentage of disk bandwidth consumed per minute |`disk_bandwidth_consumed_percentage` |Percent |Average |No Dimensions |Yes|
|Disk IOPS Consumed Percentage<p><p>Percentage of disk I/Os consumed per minute |`disk_iops_consumed_percentage` |Percent |Average |No Dimensions |Yes|
|Disk Queue Depth<p><p>Number of outstanding I/O operations to the data disk |`disk_queue_depth` |Count |Average |No Dimensions |Yes|
|IOPS<p><p>IO Operations per second |`iops` |Count |Average |No Dimensions |Yes|
|Database Is Alive<p><p>Indicates if the database is up or not |`is_db_alive` |Count |Maximum |No Dimensions |Yes|
|Max Logical Replication Lag<p><p>Maximum lag across all logical replication slots |`logical_replication_delay_in_bytes` |Bytes |Maximum |No Dimensions |Yes|
|Oldest Query<p><p>The age in seconds of the longest query that is currently running |`longest_query_time_sec` |Seconds |Maximum |No Dimensions |Yes|
|Oldest Transaction<p><p>The age in seconds of the longest transaction (including idle transactions) |`longest_transaction_time_sec` |Seconds |Maximum |No Dimensions |Yes|
|Max Connections<p><p>Max connections |`max_connections` |Count |Maximum |No Dimensions |Yes|
|Maximum Used Transaction IDs<p><p>Maximum Used Transaction IDs |`maximum_used_transactionIDs` |Count |Average |No Dimensions |Yes|
|Memory percent<p><p>Memory percent |`memory_percent` |Percent |Average |No Dimensions |Yes|
|Estimated Dead Rows User Tables<p><p>Estimated number of dead rows for user only tables in this database |`n_dead_tup_user_tables` |Count |Maximum |DatabaseName |Yes|
|Estimated Live Rows User Tables<p><p>Estimated number of live rows for user only tables in this database |`n_live_tup_user_tables` |Count |Maximum |DatabaseName |Yes|
|Estimated Modifications User Tables<p><p>Estimated number of rows modified since user only tables were last analyzed |`n_mod_since_analyze_user_tables` |Count |Maximum |DatabaseName |Yes|
|Network Out<p><p>Network Out across active connections |`network_bytes_egress` |Bytes |Total |No Dimensions |Yes|
|Network In<p><p>Network In across active connections |`network_bytes_ingress` |Bytes |Total |No Dimensions |Yes|
|Number of connection pools<p><p>Total number of connection pools |`num_pools` |Count |Maximum |DatabaseName |Yes|
|Backends<p><p>Number of backends connected to this database |`numbackends` |Count |Maximum |DatabaseName |Yes|
|Oldest Backend<p><p>The age in seconds of the oldest backend (irrespective of the state) |`oldest_backend_time_sec` |Seconds |Maximum |No Dimensions |Yes|
|Oldest xmin<p><p>The actual value of the oldest xmin. |`oldest_backend_xmin` |Count |Maximum |No Dimensions |Yes|
|Oldest xmin Age<p><p>Age in units of the oldest xmin. It indicated how many transactions passed since oldest xmin |`oldest_backend_xmin_age` |Count |Maximum |No Dimensions |Yes|
|Max Physical Replication Lag<p><p>Maximum lag across all asynchronous physical replication slots |`physical_replication_delay_in_bytes` |Bytes |Maximum |No Dimensions |Yes|
|Read Replica Lag<p><p>Read Replica lag in seconds |`physical_replication_delay_in_seconds` |Seconds |Maximum |No Dimensions |Yes|
|Read IOPS<p><p>Number of data disk I/O read operations per second |`read_iops` |Count |Average |No Dimensions |Yes|
|Read Throughput Bytes/Sec<p><p>Bytes read per second from the data disk during monitoring period |`read_throughput` |Count |Average |No Dimensions |Yes|
|Active server connections<p><p>Connections to PostgreSQL that are in use by a client connection |`server_connections_active` |Count |Maximum |DatabaseName |Yes|
|Idle server connections<p><p>Connections to PostgreSQL that are idle, ready to service a new client connection |`server_connections_idle` |Count |Maximum |DatabaseName |Yes|
|Sessions by State<p><p>Overall state of the backends |`sessions_by_state` |Count |Maximum |State |Yes|
|Sessions by WaitEventType<p><p>Sessions by the type of event for which the backend is waiting |`sessions_by_wait_event_type` |Count |Maximum |WaitEventType |Yes|
|Storage Free<p><p>Storage Free |`storage_free` |Bytes |Average |No Dimensions |Yes|
|Storage percent<p><p>Storage percent |`storage_percent` |Percent |Average |No Dimensions |Yes|
|Storage used<p><p>Storage used |`storage_used` |Bytes |Average |No Dimensions |Yes|
|User Tables Analyzed<p><p>Number of user only tables that have been analyzed in this database |`tables_analyzed_user_tables` |Count |Maximum |DatabaseName |Yes|
|User Tables AutoAnalyzed<p><p>Number of user only tables that have been analyzed by the autovacuum daemon in this database |`tables_autoanalyzed_user_tables` |Count |Maximum |DatabaseName |Yes|
|User Tables AutoVacuumed<p><p>Number of user only tables that have been vacuumed by the autovacuum daemon in this database |`tables_autovacuumed_user_tables` |Count |Maximum |DatabaseName |Yes|
|User Tables Counter<p><p>Number of user only tables in this database |`tables_counter_user_tables` |Count |Maximum |DatabaseName |Yes|
|User Tables Vacuumed<p><p>Number of user only tables that have been vacuumed in this database |`tables_vacuumed_user_tables` |Count |Maximum |DatabaseName |Yes|
|Temporary Files Size<p><p>Total amount of data written to temporary files by queries in this database |`temp_bytes` |Bytes |Total |DatabaseName |Yes|
|Temporary Files<p><p>Number of temporary files created by queries in this database |`temp_files` |Count |Total |DatabaseName |Yes|
|Total pooled connections<p><p>Current number of pooled connections |`total_pooled_connections` |Count |Maximum |DatabaseName |Yes|
|Transactions per second (Preview)<p><p>Number of transactions executed within a second |`tps` |Count |Maximum |DatabaseName |Yes|
|Tuples Deleted<p><p>Number of rows deleted by queries in this database |`tup_deleted` |Count |Total |DatabaseName |Yes|
|Tuples Fetched<p><p>Number of rows fetched by queries in this database |`tup_fetched` |Count |Total |DatabaseName |Yes|
|Tuples Inserted<p><p>Number of rows inserted by queries in this database |`tup_inserted` |Count |Total |DatabaseName |Yes|
|Tuples Returned<p><p>Number of rows returned by queries in this database |`tup_returned` |Count |Total |DatabaseName |Yes|
|Tuples Updated<p><p>Number of rows updated by queries in this database |`tup_updated` |Count |Total |DatabaseName |Yes|
|Transaction Log Storage Used<p><p>Transaction Log Storage Used |`txlogs_storage_used` |Bytes |Average |No Dimensions |Yes|
|Vacuum Counter User Tables<p><p>Number of times user only tables have been manually vacuumed in this database (not counting VACUUM FULL) |`vacuum_count_user_tables` |Count |Maximum |DatabaseName |Yes|
|Write IOPS<p><p>Number of data disk I/O write operations per second |`write_iops` |Count |Average |No Dimensions |Yes|
|Write Throughput Bytes/Sec<p><p>Bytes written per second to the data disk during monitoring period |`write_throughput` |Count |Average |No Dimensions |Yes|
|Transactions Committed<p><p>Number of transactions in this database that have been committed |`xact_commit` |Count |Total |DatabaseName |Yes|
|Transactions Rolled Back<p><p>Number of transactions in this database that have been rolled back |`xact_rollback` |Count |Total |DatabaseName |Yes|
|Total Transactions<p><p>Number of total transactions executed in this database |`xact_total` |Count |Total |DatabaseName |Yes|


<!--Gen Date:  Mon Sep 04 2023 13:11:00 GMT+0300 (Israel Daylight Time)-->