---
title: Azure Monitor Logs reference - HDInsightSparkTaskEvents
description: Reference for HDInsightSparkTaskEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# HDInsightSparkTaskEvents

 Spark Task Events.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- HDInsight Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationId | string | The application ID of the application producing the record. |
| AttemptId | string | The ID of task attempt. |
| BytesRead | long | The number bytes read during the task. |
| BytesWritten | long | The number of bytes written by the task. |
| ClusterDnsName | string | The DNS name of the cluster running the task. |
| ClusterTenantId | string | The tenant ID of the cluster running the task. |
| DiskBytesSpilled | long | The number of disk bytes spilled. |
| EndReason | string | Reason why the task ended. |
| ExecutorCPUTime | long | The CPU time consumed by the task executor. |
| ExecutorDeserializeCPUTime | long | The CPU time the task executor spent deserializing. |
| ExecutorDeserializeTime | long | The time the task executor spent deserializing. |
| ExecutorId | string | The ID executor. |
| ExecutorRunTime | long | The time task executor spent running. |
| Failed | bool | Boolean describing whether the task failed. |
| FinishTime | datetime | The time (UTC) the task finished. |
| Host | string | The FQDN of the host running the task. |
| InputMetrics | long | The metrics associated with the task input. |
| IpAddress | string | The IP Address of the node running the task. |
| JvmGcTime | long | The time the JVM spent garbage collecting. |
| Killed | bool | Boolean describing whether the task was killed. |
| LaunchTime | datetime | The time (UTC) the task was launched. |
| MemoryBytesSpilled | long | The bytes of memory spilled. |
| NumUpdatedBlockStatuses | long | The number updated block statuses during the task. |
| OutputMetrics | long | The metrics associated with the task output. |
| PeakExecutionMemory | long | The peak amount of memory used during execution. |
| RecordsRead | long | The number of records read during the task. |
| RecordsWritten | long | The number of records written by the task. |
| Region | string | The region of the cluster running the task. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSerializationTime | long | The serialization time spent while getting the result. |
| ResultSize | long | Size of the result. |
| Role | string | The type of node running the task. |
| SchedulerDelay | long | The amount of delay the scheduler experienced. |
| ShuffleBytesWritten | long | The bytes written during the shuffle task. |
| ShuffleFetchWaitTime | long | The time spent waitng for fetching. |
| ShuffleLocalBlocksFetched | long | The number of local blocks fethced during the shuffle task. |
| ShuffleReadMetrics | long | The metrics associated with shuffle reads. |
| ShuffleRecordsWritten | long | The number of records written during the shuffle task. |
| ShuffleRemoteBlocksFetched | long | The number of remote blocks fethced during the shuffle task. |
| ShuffleTotalBlocksFetched | long | The number of blocks fethced during the shuffle task. |
| ShuffleTotalBytesRead | long | The number bytes read during the shuffle task. |
| ShuffleWriteMetrics | long | The metrics associated with shuffle writes. |
| ShuffleWriteTime | long | The time spent writing during the shuffle task. |
| SourceSystem | string |  |
| StageId | string | The ID of the stage associated with the task. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TaskId | string | The ID of the task. |
| TaskType | string | The task type. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UpdatedBlocks | long | The number of updated blocks. |
| UserSubscriptionId | string | The subscription ID of the cluster running the task |
