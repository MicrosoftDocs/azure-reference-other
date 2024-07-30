---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.DBforMariaDB/servers, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Active Connections**<br><br>Active Connections |`active_connections` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Backup Storage used**<br><br>Backup Storage used |`backup_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Errors|**Failed Connections**<br><br>Failed Connections |`connections_failed` |Count |Total |\<none\>|PT1M |Yes|
|Saturation|**CPU percent**<br><br>CPU percent |`cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**IO percent**<br><br>IO percent |`io_consumption_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Memory percent**<br><br>Memory percent |`memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Network Out**<br><br>Network Out across active connections |`network_bytes_egress` |Bytes |Total |\<none\>|PT1M |Yes|
|Traffic|**Network In**<br><br>Network In across active connections |`network_bytes_ingress` |Bytes |Total |\<none\>|PT1M |Yes|
|Latency|**Replication lag in seconds**<br><br>Replication lag in seconds |`seconds_behind_master` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Server Log storage limit**<br><br>Server Log storage limit |`serverlog_storage_limit` |Bytes |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Server Log storage percent**<br><br>Server Log storage percent |`serverlog_storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Server Log storage used**<br><br>Server Log storage used |`serverlog_storage_usage` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Storage limit**<br><br>Storage limit |`storage_limit` |Bytes |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Storage percent**<br><br>Storage percent |`storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Storage used**<br><br>Storage used |`storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|