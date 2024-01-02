---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ContainerInstance/containerScaleSets, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Percentage CPU**<p><p>Average of the CPU percentages consumed by individual Container Groups in this Scale Set |`CpuPercentage` |Percent |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**CPU usage**<p><p>Average of the CPU utilizations in millicores consumed by Container Groups in this Scale Set |`CpuUsage` |MilliCores |Total, Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**Memory percentage**<p><p>Average of the memory percentages consumed ((usedMemory/allocatedMemory) * 100) by Container Groups in this Scale Set |`MemoryPercentage` |Percent |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**Memory usage**<p><p>Total memory used by all the Container Groups in this Scale Set |`MemoryUsage` |Bytes |Total, Average, Minimum, Maximum |\<none\>|PT1M |Yes|