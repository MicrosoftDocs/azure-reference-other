---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ContainerInstance/containerScaleSets, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Percentage CPU**<br><br>Average of the CPU percentages consumed by individual Container Groups in this Scale Set |`CpuPercentage` |Percent |Average, Minimum, Maximum |`containerName`|PT1M |Yes|
|**CPU usage**<br><br>Average of the CPU utilizations in millicores consumed by Container Groups in this Scale Set |`CpuUsage` |MilliCores |Total, Average, Minimum, Maximum |`containerName`|PT1M |Yes|
|**Memory percentage**<br><br>Average of the memory percentages consumed ((usedMemory/allocatedMemory) * 100) by Container Groups in this Scale Set |`MemoryPercentage` |Percent |Average, Minimum, Maximum |`containerName`|PT1M |Yes|
|**Memory usage**<br><br>Total memory used by all the Container Groups in this Scale Set |`MemoryUsage` |Bytes |Total, Average, Minimum, Maximum |`containerName`|PT1M |Yes|