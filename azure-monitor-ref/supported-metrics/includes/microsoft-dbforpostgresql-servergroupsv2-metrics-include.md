---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DBForPostgreSQL/serverGroupsv2, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Active Connections**<br><br>Active Connections |`active_connections` |Count |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|Saturation|**Reserved Memory percent**<br><br>Percentage of Commit Memory Limit Reserved by Applications |`apps_reserved_memory_percent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|Saturation|**CPU Credits Consumed**<br><br>Total number of credits consumed by the node. Only available when burstable compute is provisioned on the node. |`cpu_credits_consumed` |Count |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|Saturation|**CPU Credits Remaining**<br><br>Total number of credits available to burst. Only available when burstable compute is provisioned on the node. |`cpu_credits_remaining` |Count |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|Saturation|**CPU percent**<br><br>CPU percent |`cpu_percent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|Traffic|**IOPS**<br><br>IO operations per second |`iops` |Count |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|Saturation|**Memory percent**<br><br>Memory percent |`memory_percent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|Traffic|**Network Out**<br><br>Network Out across active connections |`network_bytes_egress` |Bytes |Total |`ServerName`|PT1M |Yes|
|Traffic|**Network In**<br><br>Network In across active connections |`network_bytes_ingress` |Bytes |Total |`ServerName`|PT1M |Yes|
|Latency|**Replication lag**<br><br>Allows to see how much read replica nodes are behind their counterparts in the primary cluster |`replication_lag` |MilliSeconds |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|Saturation|**Storage percent**<br><br>Storage percent |`storage_percent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|Saturation|**Storage used**<br><br>Storage used |`storage_used` |Bytes |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|Saturation|**VM Cached Bandwidth Consumed Percentage**<br><br>Percentage of cached disk bandwidth consumed by the VM |`vm_cached_bandwidth_percent` |Percent |Average |`ServerName`|PT1M |Yes|
|Saturation|**VM Cached IOPS Consumed Percentage**<br><br>Percentage of cached disk IOPS consumed by the VM |`vm_cached_iops_percent` |Percent |Average |`ServerName`|PT1M |Yes|
|Saturation|**VM Uncached Bandwidth Consumed Percentage**<br><br>Percentage of uncached disk bandwidth consumed by the VM |`vm_uncached_bandwidth_percent` |Percent |Average |`ServerName`|PT1M |Yes|
|Saturation|**VM Uncached IOPS Consumed Percentage**<br><br>Percentage of uncached disk IOPS consumed by the VM |`vm_uncached_iops_percent` |Percent |Average |`ServerName`|PT1M |Yes|