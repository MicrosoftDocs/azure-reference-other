---
ms.service: azure-monitor
ms.topic: include
ms.date: 12/01/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.App/containerapps, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Reserved Cores**<p><p>Number of reserved cores for container app revisions |`CoresQuotaUsed` |Count |Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Replica Count**<p><p>Number of replicas count of container app |`Replicas` |Count |Average, Total, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Requests**<p><p>Requests processed |`Requests` |Count |Average, Total, Maximum, Minimum |`revisionName`, `podName`, `statusCodeCategory`, `statusCode`|PT1M |Yes|
|**Resiliency Connection Timeouts**<p><p>Total connection timeouts |`ResiliencyConnectTimeouts` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Resiliency Ejected Hosts**<p><p>Number of currently ejected hosts |`ResiliencyEjectedHosts` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Resiliency Ejections Aborted**<p><p>Number of ejections aborted due to the max ejection % |`ResiliencyEjectionsAborted` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Resiliency Request Retries**<p><p>Total request retries |`ResiliencyRequestRetries` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Resiliency Requests Pending Connection Pool**<p><p>Total requests pending a connection pool connection |`ResiliencyRequestsPendingConnectionPool` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Resiliency Request Timeouts**<p><p>Total request that timed out waiting for a response |`ResiliencyRequestTimeouts` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|**Replica Restart Count**<p><p>Restart count of container app replicas |`RestartCount` |Count |Average, Total, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|**Network In Bytes**<p><p>Network received bytes |`RxBytes` |Bytes |Average, Total, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|**Total Reserved Cores**<p><p>Number of total reserved cores for the container app |`TotalCoresQuotaUsed` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Network Out Bytes**<p><p>Network transmitted bytes |`TxBytes` |Bytes |Average, Total, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|**CPU Usage**<p><p>CPU consumed by the container app, in nano cores. 1,000,000,000 nano cores = 1 core |`UsageNanoCores` |NanoCores |Total, Average, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|**Memory Working Set Bytes**<p><p>Container App working set memory used in bytes. |`WorkingSetBytes` |Bytes |Total, Average, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|