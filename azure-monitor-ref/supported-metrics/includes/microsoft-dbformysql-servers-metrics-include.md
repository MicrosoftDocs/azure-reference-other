---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DBforMySQL/servers, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Active Connections**<p><p>Active Connections |`active_connections` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Backup Storage used**<p><p>Backup Storage used |`backup_storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Failed Connections**<p><p>Failed Connections |`connections_failed` |Count |Total |\<none\>|PT1M |Yes|
|**CPU percent**<p><p>CPU percent |`cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**IO percent**<p><p>IO percent |`io_consumption_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Memory percent**<p><p>Memory percent |`memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Network Out**<p><p>Network Out across active connections |`network_bytes_egress` |Bytes |Total |\<none\>|PT1M |Yes|
|**Network In**<p><p>Network In across active connections |`network_bytes_ingress` |Bytes |Total |\<none\>|PT1M |Yes|
|**Replication lag in seconds**<p><p>Replication lag in seconds |`seconds_behind_master` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Server Log storage limit**<p><p>Server Log storage limit |`serverlog_storage_limit` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Server Log storage percent**<p><p>Server Log storage percent |`serverlog_storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Server Log storage used**<p><p>Server Log storage used |`serverlog_storage_usage` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Storage limit**<p><p>Storage limit |`storage_limit` |Bytes |Maximum |\<none\>|PT1M |Yes|
|**Storage percent**<p><p>Storage percent |`storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Storage used**<p><p>Storage used |`storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|