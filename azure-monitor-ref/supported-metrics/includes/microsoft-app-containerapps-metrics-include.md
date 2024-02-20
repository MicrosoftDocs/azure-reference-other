---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.App/containerapps, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Reserved Cores**<br><br>Number of reserved cores for container app revisions |`CoresQuotaUsed` |Count |Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Replica Count**<br><br>Number of replicas count of container app |`Replicas` |Count |Average, Total, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Requests**<br><br>Requests processed |`Requests` |Count |Average, Total, Maximum, Minimum |`revisionName`, `podName`, `statusCodeCategory`, `statusCode`|PT1M |Yes|
|**Resiliency Connection Timeouts**<br><br>Total connection timeouts |`ResiliencyConnectTimeouts` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Resiliency Ejected Hosts**<br><br>Number of currently ejected hosts |`ResiliencyEjectedHosts` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Resiliency Ejections Aborted**<br><br>Number of ejections aborted due to the max ejection % |`ResiliencyEjectionsAborted` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Resiliency Request Retries**<br><br>Total request retries |`ResiliencyRequestRetries` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Resiliency Requests Pending Connection Pool**<br><br>Total requests pending a connection pool connection |`ResiliencyRequestsPendingConnectionPool` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Resiliency Request Timeouts**<br><br>Total request that timed out waiting for a response |`ResiliencyRequestTimeouts` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Replica Restart Count**<br><br>Restart count of container app replicas |`RestartCount` |Count |Average, Total, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|**Network In Bytes**<br><br>Network received bytes |`RxBytes` |Bytes |Average, Total, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|**Total Reserved Cores**<br><br>Number of total reserved cores for the container app |`TotalCoresQuotaUsed` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Network Out Bytes**<br><br>Network transmitted bytes |`TxBytes` |Bytes |Average, Total, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|**CPU Usage**<br><br>CPU consumed by the container app, in nano cores. 1,000,000,000 nano cores = 1 core |`UsageNanoCores` |NanoCores |Total, Average, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|**Memory Working Set Bytes**<br><br>Container App working set memory used in bytes. |`WorkingSetBytes` |Bytes |Total, Average, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|