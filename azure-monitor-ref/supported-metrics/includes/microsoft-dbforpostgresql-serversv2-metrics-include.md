---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DBforPostgreSQL/serversv2, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Active Connections**<br><br>Active Connections |`active_connections` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**CPU percent**<br><br>CPU percent |`cpu_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**IOPS**<br><br>IO Operations per second |`iops` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Memory percent**<br><br>Memory percent |`memory_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Traffic|**Network Out**<br><br>Network Out across active connections |`network_bytes_egress` |Bytes |Total |\<none\>|PT1M |Yes|
|Traffic|**Network In**<br><br>Network In across active connections |`network_bytes_ingress` |Bytes |Total |\<none\>|PT1M |Yes|
|Saturation|**Storage percent**<br><br>Storage percent |`storage_percent` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Saturation|**Storage used**<br><br>Storage used |`storage_used` |Bytes |Average, Maximum, Minimum |\<none\>|PT1M |Yes|