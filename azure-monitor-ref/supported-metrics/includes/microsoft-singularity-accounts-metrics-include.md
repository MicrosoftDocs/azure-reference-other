---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.singularity/accounts, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|GpuUtilizationPercentage<p><p>GPU utilization percentage |`GpuUtilizationPercentage` |Percent |Average |accountname, ClusterName, Environment, instance, jobContainerId, jobInstanceId, jobname, Region|PT1M |Yes|