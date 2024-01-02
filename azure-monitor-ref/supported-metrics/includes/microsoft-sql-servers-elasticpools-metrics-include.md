---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Sql/servers/elasticpools, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Data space allocated**<p><p>Data space allocated. Not applicable to hyperscale |`allocated_data_storage` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Data space allocated percent**<p><p>Data space allocated percent. Not applicable to hyperscale |`allocated_data_storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**App CPU billed**<p><p>App CPU billed. Applies to serverless elastic pools. |`app_cpu_billed` |Count |Total |\<none\>|PT1M |Yes|
|**App CPU percentage**<p><p>App CPU percentage. Applies to serverless elastic pools. |`app_cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**App memory percentage**<p><p>App memory percentage. Applies to serverless elastic pools. |`app_memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**CPU limit**<p><p>CPU limit. Applies to vCore-based elastic pools. |`cpu_limit` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**CPU percentage**<p><p>CPU percentage |`cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**CPU used**<p><p>CPU used. Applies to vCore-based elastic pools. |`cpu_used` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**DTU percentage**<p><p>DTU Percentage. Applies to DTU-based elastic pools. |`dtu_consumption_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**eDTU limit**<p><p>eDTU limit. Applies to DTU-based elastic pools. |`eDTU_limit` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**eDTU used**<p><p>eDTU used. Applies to DTU-based elastic pools. |`eDTU_used` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Log IO percentage**<p><p>Log IO percentage |`log_write_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Data IO percentage**<p><p>Data IO percentage |`physical_data_read_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Sessions Count**<p><p>Number of active sessions |`sessions_count` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Sessions percentage**<p><p>Sessions percentage |`sessions_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**SQL instance CPU percent**<p><p>CPU usage by all user and system workloads. Applies to elastic pools. |`sql_instance_cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**SQL instance memory percent**<p><p>Memory usage by the database engine instance. Applies to elastic pools. |`sql_instance_memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**SQL Server process core percent**<p><p>CPU usage as a percentage of the SQL DB process. Applies to elastic pools. (This metric is equivalent to sql_instance_cpu_percent, and will be removed in the future.) |`sqlserver_process_core_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**SQL Server process memory percent**<p><p>Memory usage as a percentage of the SQL DB process. Applies to elastic pools. (This metric is equivalent to sql_instance_memory_percent, and will be removed in the future.) |`sqlserver_process_memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Data max size**<p><p>Data max size. Not applicable to hyperscale |`storage_limit` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Data space used percent**<p><p>Data space used percent. Not applicable to hyperscale |`storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Data space used**<p><p>Data space used. Not applicable to hyperscale |`storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Tempdb Data File Size Kilobytes**<p><p>Space used in tempdb data files in kilobytes. |`tempdb_data_size` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Tempdb Log File Size Kilobytes**<p><p>Space used in tempdb transaction log file in kilobytes. |`tempdb_log_size` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Tempdb Percent Log Used**<p><p>Space used percentage in tempdb transaction log file |`tempdb_log_used_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Workers percentage**<p><p>Workers percentage |`workers_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**In-Memory OLTP storage percent**<p><p>In-Memory OLTP storage percent. Not applicable to hyperscale |`xtp_storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|