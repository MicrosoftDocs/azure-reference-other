---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/01/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.App/jobs, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Basic|**Job Executions**<br><br>Executions run by the Container Apps Job |`Executions` |Count |Average, Total, Maximum, Minimum |`state`, `jobName`, `executionName`|PT1M |Yes|
|Basic|**Usage Bytes**<br><br>Container App Job memory used in bytes. |`Usage Bytes` |Bytes |Total, Average, Maximum, Minimum |`state`, `jobName`, `executionName`|PT1M |Yes|
|Basic|**CPU Usage**<br><br>CPU consumed by the container app job, in nano cores. 1,000,000,000 nano cores = 1 core |`UsageNanoCores` |NanoCores |Total, Average, Maximum, Minimum |`state`, `jobName`, `executionName`|PT1M |Yes|