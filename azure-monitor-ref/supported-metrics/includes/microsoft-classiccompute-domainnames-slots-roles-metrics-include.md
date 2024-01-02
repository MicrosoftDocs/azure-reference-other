---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ClassicCompute/domainNames/slots/roles, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Disk Read**<p><p>Average bytes read from disk during monitoring period. |`Disk Read Bytes/Sec` |BytesPerSecond |Average |`RoleInstanceId`|PT1M |No|
|**Disk Read Operations/Sec**<p><p>Disk Read IOPS. |`Disk Read Operations/Sec` |CountPerSecond |Average |`RoleInstanceId`|PT1M |Yes|
|**Disk Write**<p><p>Average bytes written to disk during monitoring period. |`Disk Write Bytes/Sec` |BytesPerSecond |Average |`RoleInstanceId`|PT1M |No|
|**Disk Write Operations/Sec**<p><p>Disk Write IOPS. |`Disk Write Operations/Sec` |CountPerSecond |Average |`RoleInstanceId`|PT1M |Yes|
|**Network In**<p><p>The number of bytes received on all network interfaces by the Virtual Machine(s) (Incoming Traffic). |`Network In` |Bytes |Total |`RoleInstanceId`|PT1M |Yes|
|**Network Out**<p><p>The number of bytes out on all network interfaces by the Virtual Machine(s) (Outgoing Traffic). |`Network Out` |Bytes |Total |`RoleInstanceId`|PT1M |Yes|
|**Percentage CPU**<p><p>The percentage of allocated compute units that are currently in use by the Virtual Machine(s). |`Percentage CPU` |Percent |Average |`RoleInstanceId`|PT1M |Yes|