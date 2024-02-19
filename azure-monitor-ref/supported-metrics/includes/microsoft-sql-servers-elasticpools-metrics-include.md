---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Sql/servers/elasticpools, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Basic|**Data space allocated**<br><br>Data space allocated. Not applicable to hyperscale |`allocated_data_storage` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Data space allocated percent**<br><br>Data space allocated percent. Not applicable to hyperscale |`allocated_data_storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**App CPU billed**<br><br>App CPU billed. Applies to serverless elastic pools. |`app_cpu_billed` |Count |Total |\<none\>|PT1M |Yes|
|Basic|**App CPU percentage**<br><br>App CPU percentage. Applies to serverless elastic pools. |`app_cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**App memory percentage**<br><br>App memory percentage. Applies to serverless elastic pools. |`app_memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**CPU limit**<br><br>CPU limit. Applies to vCore-based elastic pools. |`cpu_limit` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**CPU percentage**<br><br>CPU percentage |`cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**CPU used**<br><br>CPU used. Applies to vCore-based elastic pools. |`cpu_used` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**DTU percentage**<br><br>DTU Percentage. Applies to DTU-based elastic pools. |`dtu_consumption_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**eDTU limit**<br><br>eDTU limit. Applies to DTU-based elastic pools. |`eDTU_limit` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**eDTU used**<br><br>eDTU used. Applies to DTU-based elastic pools. |`eDTU_used` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Log IO percentage**<br><br>Log IO percentage |`log_write_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Data IO percentage**<br><br>Data IO percentage |`physical_data_read_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Sessions Count**<br><br>Number of active sessions |`sessions_count` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Sessions percentage**<br><br>Sessions percentage |`sessions_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|InstanceAndAppAdvanced|**SQL instance CPU percent**<br><br>CPU usage by all user and system workloads. Applies to elastic pools. |`sql_instance_cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|InstanceAndAppAdvanced|**SQL instance memory percent**<br><br>Memory usage by the database engine instance. Applies to elastic pools. |`sql_instance_memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|InstanceAndAppAdvanced|**SQL Server process core percent**<br><br>CPU usage as a percentage of the SQL DB process. Applies to elastic pools. (This metric is equivalent to sql_instance_cpu_percent, and will be removed in the future.) |`sqlserver_process_core_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|InstanceAndAppAdvanced|**SQL Server process memory percent**<br><br>Memory usage as a percentage of the SQL DB process. Applies to elastic pools. (This metric is equivalent to sql_instance_memory_percent, and will be removed in the future.) |`sqlserver_process_memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Data max size**<br><br>Data max size. Not applicable to hyperscale |`storage_limit` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Data space used percent**<br><br>Data space used percent. Not applicable to hyperscale |`storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Data space used**<br><br>Data space used. Not applicable to hyperscale |`storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|InstanceAndAppAdvanced|**Tempdb Data File Size Kilobytes**<br><br>Space used in tempdb data files in kilobytes. |`tempdb_data_size` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|InstanceAndAppAdvanced|**Tempdb Log File Size Kilobytes**<br><br>Space used in tempdb transaction log file in kilobytes. |`tempdb_log_size` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|InstanceAndAppAdvanced|**Tempdb Percent Log Used**<br><br>Space used percentage in tempdb transaction log file |`tempdb_log_used_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Workers percentage**<br><br>Workers percentage |`workers_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**In-Memory OLTP storage percent**<br><br>In-Memory OLTP storage percent. Not applicable to hyperscale |`xtp_storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|