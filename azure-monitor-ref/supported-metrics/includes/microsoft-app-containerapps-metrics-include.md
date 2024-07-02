---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/01/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.App/containerapps, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Basic|**Reserved Cores**<br><br>Number of reserved cores for container app revisions |`CoresQuotaUsed` |Count |Maximum, Minimum |`revisionName`|PT1M |Yes|
|Java|**jvm.buffer.count**<br><br>Number of buffers in the memory pool |`JvmBufferCount` |Count |Average, Maximum, Minimum |`revisionName`, `podName`, `container`, `poolName`|PT1M |Yes|
|Java|**jvm.buffer.memory.limit**<br><br>Amount of total memory capacity of buffers (in bytes) |`JvmBufferMemoryLimit` |Bytes |Average, Maximum, Minimum |`revisionName`, `podName`, `container`, `poolName`|PT1M |Yes|
|Java|**jvm.buffer.memory.usage**<br><br>Amount of memory used by buffers, such as direct memory (in bytes) |`JvmBufferMemoryUsage` |Bytes |Average, Maximum, Minimum |`revisionName`, `podName`, `container`, `poolName`|PT1M |Yes|
|Java|**jvm.gc.count**<br><br>Count of JVM garbage collection actions |`JvmGcCount` |Count |Total, Average, Maximum, Minimum |`revisionName`, `podName`, `container`, `gcName`|PT1M |Yes|
|Java|**jvm.gc.duration**<br><br>Duration of JVM garbage collection actions (in milliseconds) |`JvmGcDuration` |Milliseconds |Total, Average, Maximum, Minimum |`revisionName`, `podName`, `container`, `gcName`|PT1M |Yes|
|Java|**jvm.memory.committed**<br><br>Amount of memory guaranteed to be available for each pool (in bytes) |`JvmMemoryCommitted` |Bytes |Average, Maximum, Minimum |`revisionName`, `podName`, `container`, `poolName`, `poolType`|PT1M |Yes|
|Java|**jvm.memory.limit**<br><br>Amount of maximum obtainable memory for each pool (in bytes) |`JvmMemoryLimit` |Bytes |Average, Maximum, Minimum |`revisionName`, `podName`, `container`, `poolName`, `poolType`|PT1M |Yes|
|Java|**jvm.memory.total.committed**<br><br>Total amount of memory guaranteed to be available for heap or non-heap (in bytes) |`JvmMemoryTotalCommitted` |Bytes |Average, Maximum, Minimum |`revisionName`, `podName`, `container`, `poolType`|PT1M |Yes|
|Java|**jvm.memory.total.limit**<br><br>Total amount of maximum obtainable memory for heap or non-heap (in bytes) |`JvmMemoryTotalLimit` |Bytes |Average, Maximum, Minimum |`revisionName`, `podName`, `container`, `poolType`|PT1M |Yes|
|Java|**jvm.memory.total.used**<br><br>Total amount of memory used by heap or non-heap (in bytes) |`JvmMemoryTotalUsed` |Bytes |Average, Maximum, Minimum |`revisionName`, `podName`, `container`, `poolType`|PT1M |Yes|
|Java|**jvm.memory.used**<br><br>Amount of memory used by each pool (in bytes) |`JvmMemoryUsed` |Bytes |Average, Maximum, Minimum |`revisionName`, `podName`, `container`, `poolName`, `poolType`|PT1M |Yes|
|Java|**jvm.thread.count**<br><br>Number of executing platform threads |`JvmThreadCount` |Count |Average, Maximum, Minimum |`revisionName`, `podName`, `container`, `daemon`, `threadState`|PT1M |Yes|
|Basic|**Replica Count**<br><br>Number of replicas count of container app |`Replicas` |Count |Average, Total, Maximum, Minimum |`revisionName`|PT1M |Yes|
|Basic|**Requests**<br><br>Requests processed |`Requests` |Count |Average, Total, Maximum, Minimum |`revisionName`, `podName`, `statusCodeCategory`, `statusCode`|PT1M |Yes|
|Basic|**Resiliency Connection Timeouts**<br><br>Total connection timeouts |`ResiliencyConnectTimeouts` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|Basic|**Resiliency Ejected Hosts**<br><br>Number of currently ejected hosts |`ResiliencyEjectedHosts` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|Basic|**Resiliency Ejections Aborted**<br><br>Number of ejections aborted due to the max ejection % |`ResiliencyEjectionsAborted` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|Basic|**Resiliency Request Retries**<br><br>Total request retries |`ResiliencyRequestRetries` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|Basic|**Resiliency Requests Pending Connection Pool**<br><br>Total requests pending a connection pool connection |`ResiliencyRequestsPendingConnectionPool` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|Basic|**Resiliency Request Timeouts**<br><br>Total request that timed out waiting for a response |`ResiliencyRequestTimeouts` |Count |Total, Average, Maximum, Minimum |`revisionName`|PT1M |Yes|
|Basic|**Replica Restart Count**<br><br>Restart count of container app replicas |`RestartCount` |Count |Average, Total, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|Basic|**Network In Bytes**<br><br>Network received bytes |`RxBytes` |Bytes |Average, Total, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|Basic|**Total Reserved Cores**<br><br>Number of total reserved cores for the container app |`TotalCoresQuotaUsed` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Basic|**Network Out Bytes**<br><br>Network transmitted bytes |`TxBytes` |Bytes |Average, Total, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|Basic|**CPU Usage**<br><br>CPU consumed by the container app, in nano cores. 1,000,000,000 nano cores = 1 core |`UsageNanoCores` |NanoCores |Total, Average, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|
|Basic|**Memory Working Set Bytes**<br><br>Container App working set memory used in bytes. |`WorkingSetBytes` |Bytes |Total, Average, Maximum, Minimum |`revisionName`, `podName`|PT1M |Yes|