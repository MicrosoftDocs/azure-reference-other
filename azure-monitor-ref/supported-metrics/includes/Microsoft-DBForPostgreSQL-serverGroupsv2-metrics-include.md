---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DBForPostgreSQL/serverGroupsv2, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Active Connections**<p><p>Active Connections |`active_connections` |Count |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|**Reserved Memory percent**<p><p>Percentage of Commit Memory Limit Reserved by Applications |`apps_reserved_memory_percent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|**CPU Credits Consumed**<p><p>Total number of credits consumed by the node. Only available when burstable compute is provisioned on the node. |`cpu_credits_consumed` |Count |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|**CPU Credits Remaining**<p><p>Total number of credits available to burst. Only available when burstable compute is provisioned on the node. |`cpu_credits_remaining` |Count |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|**CPU percent**<p><p>CPU percent |`cpu_percent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|**IOPS**<p><p>IO operations per second |`iops` |Count |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|**Memory percent**<p><p>Memory percent |`memory_percent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|**Network Out**<p><p>Network Out across active connections |`network_bytes_egress` |Bytes |Total |`ServerName`|PT1M |Yes|
|**Network In**<p><p>Network In across active connections |`network_bytes_ingress` |Bytes |Total |`ServerName`|PT1M |Yes|
|**Replication lag**<p><p>Allows to see how much read replica nodes are behind their counterparts in the primary cluster |`replication_lag` |MilliSeconds |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|**Storage percent**<p><p>Storage percent |`storage_percent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|**Storage used**<p><p>Storage used |`storage_used` |Bytes |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|**VM Cached Bandwidth Consumed Percentage**<p><p>Percentage of cached disk bandwidth consumed by the VM |`vm_cached_bandwidth_percent` |Percent |Average |`ServerName`|PT1M |Yes|
|**VM Cached IOPS Consumed Percentage**<p><p>Percentage of cached disk IOPS consumed by the VM |`vm_cached_iops_percent` |Percent |Average |`ServerName`|PT1M |Yes|
|**VM Uncached Bandwidth Consumed Percentage**<p><p>Percentage of uncached disk bandwidth consumed by the VM |`vm_uncached_bandwidth_percent` |Percent |Average |`ServerName`|PT1M |Yes|
|**VM Uncached IOPS Consumed Percentage**<p><p>Percentage of uncached disk IOPS consumed by the VM |`vm_uncached_iops_percent` |Percent |Average |`ServerName`|PT1M |Yes|