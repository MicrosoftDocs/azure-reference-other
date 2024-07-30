---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.ClassicCompute/virtualMachines, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Disk Read**<br><br>Average bytes read from disk during monitoring period. |`Disk Read Bytes/Sec` |BytesPerSecond |Average |\<none\>|PT1M |No|
|**Disk Read Operations/Sec**<br><br>Disk Read IOPS. |`Disk Read Operations/Sec` |CountPerSecond |Average |\<none\>|PT1M |Yes|
|**Disk Write**<br><br>Average bytes written to disk during monitoring period. |`Disk Write Bytes/Sec` |BytesPerSecond |Average |\<none\>|PT1M |No|
|**Disk Write Operations/Sec**<br><br>Disk Write IOPS. |`Disk Write Operations/Sec` |CountPerSecond |Average |\<none\>|PT1M |Yes|
|**Network In**<br><br>The number of bytes received on all network interfaces by the Virtual Machine(s) (Incoming Traffic). |`Network In` |Bytes |Total |\<none\>|PT1M |Yes|
|**Network Out**<br><br>The number of bytes out on all network interfaces by the Virtual Machine(s) (Outgoing Traffic). |`Network Out` |Bytes |Total |\<none\>|PT1M |Yes|
|**Percentage CPU**<br><br>The percentage of allocated compute units that are currently in use by the Virtual Machine(s). |`Percentage CPU` |Percent |Average |\<none\>|PT1M |Yes|