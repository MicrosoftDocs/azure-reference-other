---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Compute/cloudservices, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Available Memory Bytes (Preview)**<p><p>Amount of physical memory, in bytes, immediately available for allocation to a process or for system use in the Virtual Machine |`Available Memory Bytes` |Bytes |Average |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Disk Read Bytes**<p><p>Bytes read from disk during monitoring period |`Disk Read Bytes` |Bytes |Total |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Disk Read Operations/Sec**<p><p>Disk Read IOPS |`Disk Read Operations/Sec` |CountPerSecond |Average |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Disk Write Bytes**<p><p>Bytes written to disk during monitoring period |`Disk Write Bytes` |Bytes |Total |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Disk Write Operations/Sec**<p><p>Disk Write IOPS |`Disk Write Operations/Sec` |CountPerSecond |Average |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Network In Total**<p><p>The number of bytes received on all network interfaces by the Virtual Machine(s) (Incoming Traffic) |`Network In Total` |Bytes |Total |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Network Out Total**<p><p>The number of bytes out on all network interfaces by the Virtual Machine(s) (Outgoing Traffic) |`Network Out Total` |Bytes |Total |`RoleInstanceId`, `RoleId`|PT1M |Yes|
|**Percentage CPU**<p><p>The percentage of allocated compute units that are currently in use by the Virtual Machine(s) |`Percentage CPU` |Percent |Average |`RoleInstanceId`, `RoleId`|PT1M |Yes|