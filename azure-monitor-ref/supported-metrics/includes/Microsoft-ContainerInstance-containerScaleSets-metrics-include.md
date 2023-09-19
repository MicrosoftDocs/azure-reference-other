---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ContainerInstance/containerScaleSets, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Percentage CPU<p><p>Average of the CPU percentages consumed by individual Container Groups in this Scale Set |`CpuPercentage` |Percent |Average, Minimum, Maximum |No Dimensions|PT1M |Yes|
|CPU usage<p><p>Average of the CPU utilizations in millicores consumed by Container Groups in this Scale Set |`CpuUsage` |MilliCores |Total, Average, Minimum, Maximum |No Dimensions|PT1M |Yes|
|Memory percentage<p><p>Average of the memory percentages consumed ((usedMemory/allocatedMemory) * 100) by Container Groups in this Scale Set |`MemoryPercentage` |Percent |Average, Minimum, Maximum |No Dimensions|PT1M |Yes|
|Memory usage<p><p>Total memory used by all the Container Groups in this Scale Set |`MemoryUsage` |Bytes |Total, Average, Minimum, Maximum |No Dimensions|PT1M |Yes|