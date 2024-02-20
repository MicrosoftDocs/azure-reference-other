---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DBforPostgreSQL/servers, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Active Connections**<br><br>Active Connections |`active_connections` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Backup Storage Used**<br><br>Backup Storage Used |`backup_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Errors|**Failed Connections**<br><br>Failed Connections |`connections_failed` |Count |Total |\<none\>|PT1M |Yes|
|Saturation|**CPU percent**<br><br>CPU percent |`cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**IO percent**<br><br>IO percent |`io_consumption_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Memory percent**<br><br>Memory percent |`memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Network Out**<br><br>Network Out across active connections |`network_bytes_egress` |Bytes |Total |\<none\>|PT1M |Yes|
|Traffic|**Network In**<br><br>Network In across active connections |`network_bytes_ingress` |Bytes |Total |\<none\>|PT1M |Yes|
|Latency|**Max Lag Across Replicas**<br><br>Lag in bytes of the most lagging replica |`pg_replica_log_delay_in_bytes` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Latency|**Replica Lag**<br><br>Replica lag in seconds |`pg_replica_log_delay_in_seconds` |Seconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Server Log storage limit**<br><br>Server Log storage limit |`serverlog_storage_limit` |Bytes |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Server Log storage percent**<br><br>Server Log storage percent |`serverlog_storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Server Log storage used**<br><br>Server Log storage used |`serverlog_storage_usage` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Storage limit**<br><br>Storage limit |`storage_limit` |Bytes |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Storage percent**<br><br>Storage percent |`storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Storage used**<br><br>Storage used |`storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|