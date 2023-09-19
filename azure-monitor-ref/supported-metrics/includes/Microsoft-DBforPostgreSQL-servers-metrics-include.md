---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DBforPostgreSQL/servers, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Active Connections<p><p>Active Connections |`active_connections` |Count |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Backup Storage Used<p><p>Backup Storage Used |`backup_storage_used` |Bytes |Average, Maximum, Minimum |No Dimensions|PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Failed Connections<p><p>Failed Connections |`connections_failed` |Count |Total |No Dimensions|PT1M |Yes|
|CPU percent<p><p>CPU percent |`cpu_percent` |Percent |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|IO percent<p><p>IO percent |`io_consumption_percent` |Percent |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Memory percent<p><p>Memory percent |`memory_percent` |Percent |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Network Out<p><p>Network Out across active connections |`network_bytes_egress` |Bytes |Total |No Dimensions|PT1M |Yes|
|Network In<p><p>Network In across active connections |`network_bytes_ingress` |Bytes |Total |No Dimensions|PT1M |Yes|
|Max Lag Across Replicas<p><p>Lag in bytes of the most lagging replica |`pg_replica_log_delay_in_bytes` |Bytes |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Replica Lag<p><p>Replica lag in seconds |`pg_replica_log_delay_in_seconds` |Seconds |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Server Log storage limit<p><p>Server Log storage limit |`serverlog_storage_limit` |Bytes |Maximum |No Dimensions|PT1M |Yes|
|Server Log storage percent<p><p>Server Log storage percent |`serverlog_storage_percent` |Percent |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Server Log storage used<p><p>Server Log storage used |`serverlog_storage_usage` |Bytes |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Storage limit<p><p>Storage limit |`storage_limit` |Bytes |Maximum |No Dimensions|PT1M |Yes|
|Storage percent<p><p>Storage percent |`storage_percent` |Percent |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Storage used<p><p>Storage used |`storage_used` |Bytes |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|