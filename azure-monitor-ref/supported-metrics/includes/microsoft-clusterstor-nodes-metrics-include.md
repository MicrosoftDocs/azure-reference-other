---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ClusterStor/nodes, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|**TotalCapacityAvailable**<br><br>The total capacity available in lustre file system |`TotalCapacityAvailable` |Bytes |Average |`filesystem_name`, `category`, `system`|PT1M |No|
|Availability|**TotalCapacityUsed**<br><br>The total capacity used in lustre file system |`TotalCapacityUsed` |Bytes |Average |`filesystem_name`, `category`, `system`|PT1M |No|
|Availability|**TotalRead**<br><br>The total lustre file system read per second |`TotalRead` |BytesPerSecond |Average |`filesystem_name`, `category`, `system`|PT1M |No|
|Availability|**TotalWrite**<br><br>The total lustre file system write per second |`TotalWrite` |BytesPerSecond |Average |`filesystem_name`, `category`, `system`|PT1M |No|