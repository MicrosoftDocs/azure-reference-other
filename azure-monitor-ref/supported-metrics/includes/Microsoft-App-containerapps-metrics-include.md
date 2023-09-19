---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.App/containerapps, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Reserved Cores<p><p>Number of reserved cores for container app revisions |`CoresQuotaUsed` |Count |Maximum, Minimum |revisionName|PT1M |Yes|
|Replica Count<p><p>Number of replicas count of container app |`Replicas` |Count |Average, Total, Maximum, Minimum |revisionName|PT1M |Yes|
|Requests<p><p>Requests processed |`Requests` |Count |Average, Total, Maximum, Minimum |revisionName, podName, statusCodeCategory, statusCode|PT1M |Yes|
|Replica Restart Count<p><p>Restart count of container app replicas |`RestartCount` |Count |Average, Total, Maximum, Minimum |revisionName, podName|PT1M |Yes|
|Network In Bytes<p><p>Network received bytes |`RxBytes` |Bytes |Average, Total, Maximum, Minimum |revisionName, podName|PT1M |Yes|
|Total Reserved Cores<p><p>Number of total reserved cores for the container app |`TotalCoresQuotaUsed` |Count |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Network Out Bytes<p><p>Network transmitted bytes |`TxBytes` |Bytes |Average, Total, Maximum, Minimum |revisionName, podName|PT1M |Yes|
|CPU Usage<p><p>CPU consumed by the container app, in nano cores. 1,000,000,000 nano cores = 1 core |`UsageNanoCores` |NanoCores |Total, Average, Maximum, Minimum |revisionName, podName|PT1M |Yes|
|Memory Working Set Bytes<p><p>Container App working set memory used in bytes. |`WorkingSetBytes` |Bytes |Total, Average, Maximum, Minimum |revisionName, podName|PT1M |Yes|