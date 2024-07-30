---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Web/containerapps, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Replica Count**<br><br>Number of replicas count of container app |`Replicas` |Count |Average, Total, Maximum, Minimum |`revisionName`, `deploymentName`|PT1M |Yes|
|**Requests**<br><br>Requests processed |`Requests` |Count |Average, Total, Maximum, Minimum |`revisionName`, `podName`, `statusCodeCategory`, `statusCode`|PT1M |Yes|
|**Replica Restart Count**<br><br>Restart count of container app replicas |`RestartCount` |Count |Average, Total, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|**Network In Bytes**<br><br>Network received bytes |`RxBytes` |Bytes |Average, Total, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|**Network Out Bytes**<br><br>Network transmitted bytes |`TxBytes` |Bytes |Average, Total, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|**CPU Usage Nanocores**<br><br>CPU consumed by the container app, in nano cores. 1,000,000,000 nano cores = 1 core |`UsageNanoCores` |NanoCores |Total, Average, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|**Memory Working Set Bytes**<br><br>Container App working set memory used in bytes. |`WorkingSetBytes` |Bytes |Total, Average, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|