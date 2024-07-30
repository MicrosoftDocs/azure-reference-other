---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Compute/cloudservices, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Available Memory Bytes (Preview)**<br><br>Amount of physical memory, in bytes, immediately available for allocation to a process or for system use in the Virtual Machine |`Available Memory Bytes` |Bytes |Average |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Disk Read Bytes**<br><br>Bytes read from disk during monitoring period |`Disk Read Bytes` |Bytes |Total |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Disk Read Operations/Sec**<br><br>Disk Read IOPS |`Disk Read Operations/Sec` |CountPerSecond |Average |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Disk Write Bytes**<br><br>Bytes written to disk during monitoring period |`Disk Write Bytes` |Bytes |Total |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Disk Write Operations/Sec**<br><br>Disk Write IOPS |`Disk Write Operations/Sec` |CountPerSecond |Average |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Network In Total**<br><br>The number of bytes received on all network interfaces by the Virtual Machine(s) (Incoming Traffic) |`Network In Total` |Bytes |Total |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Network Out Total**<br><br>The number of bytes out on all network interfaces by the Virtual Machine(s) (Outgoing Traffic) |`Network Out Total` |Bytes |Total |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Percentage CPU**<br><br>The percentage of allocated compute units that are currently in use by the Virtual Machine(s) |`Percentage CPU` |Percent |Average |`RoleInstanceId`, `RoleId`|PT1M |Yes|