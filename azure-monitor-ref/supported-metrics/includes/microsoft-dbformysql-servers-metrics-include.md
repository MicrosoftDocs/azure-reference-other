---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DBforMySQL/servers, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Active Connections**<p><p>Active Connections |`active_connections` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Backup Storage used**<p><p>Backup Storage used |`backup_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Errors|**Failed Connections**<p><p>Failed Connections |`connections_failed` |Count |Total |\<none\>|PT1M |Yes|
|Saturation|**CPU percent**<p><p>CPU percent |`cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**IO percent**<p><p>IO percent |`io_consumption_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Memory percent**<p><p>Memory percent |`memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Network Out**<p><p>Network Out across active connections |`network_bytes_egress` |Bytes |Total |\<none\>|PT1M |Yes|
|Traffic|**Network In**<p><p>Network In across active connections |`network_bytes_ingress` |Bytes |Total |\<none\>|PT1M |Yes|
|Latency|**Replication lag in seconds**<p><p>Replication lag in seconds |`seconds_behind_master` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Server Log storage limit**<p><p>Server Log storage limit |`serverlog_storage_limit` |Bytes |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Server Log storage percent**<p><p>Server Log storage percent |`serverlog_storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Server Log storage used**<p><p>Server Log storage used |`serverlog_storage_usage` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Storage limit**<p><p>Storage limit |`storage_limit` |Bytes |Maximum |\<none\>|PT1M |Yes|
|Saturation|**Storage percent**<p><p>Storage percent |`storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Storage used**<p><p>Storage used |`storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|