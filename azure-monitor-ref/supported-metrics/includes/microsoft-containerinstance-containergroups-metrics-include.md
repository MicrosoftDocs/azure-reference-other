---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ContainerInstance/containerGroups, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**CPU Usage**<br><br>CPU usage on all cores in millicores. |`CpuUsage` |Count |Maximum, Minimum, Average |`containerName`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|**Memory Usage**<br><br>Total memory usage in byte. |`MemoryUsage` |Bytes |Maximum, Minimum, Average |`containerName`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|**Network Bytes Received Per Second**<br><br>The network bytes received per second. |`NetworkBytesReceivedPerSecond` |Bytes |Maximum, Minimum, Average |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|**Network Bytes Transmitted Per Second**<br><br>The network bytes transmitted per second. |`NetworkBytesTransmittedPerSecond` |Bytes |Maximum, Minimum, Average |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|