---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.singularity/accounts, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**GpuUtilizationPercentage**<p><p>GPU utilization percentage |`GpuUtilizationPercentage` |Percent |Average |`accountname`, `ClusterName`, `Environment`, `instance`, `jobContainerId`, `jobInstanceId`, `jobname`, `Region`|PT1M |Yes|