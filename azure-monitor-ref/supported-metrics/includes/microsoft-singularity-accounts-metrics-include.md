---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: microsoft.singularity/accounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**GpuUtilizationPercentage**<br><br>GPU utilization percentage |`GpuUtilizationPercentage` |Percent |Average |`accountname`, `ClusterName`, `Environment`, `instance`, `jobContainerId`, `jobInstanceId`, `jobname`, `Region`|PT1M |Yes|