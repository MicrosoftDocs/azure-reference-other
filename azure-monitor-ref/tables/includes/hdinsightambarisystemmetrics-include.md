---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: HDInsightAmbariSystemMetrics
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| BytesIn | real | Bytes ingested in last timeframe. |
| BytesOut | real | Bytes sent out. |
| CachedMemory | real | amount of cached memory in KB. |
| ClusterName | string | Name of the cluster the host belongs to. |
| ClusterType | string | Type of cluster the record came from. |
| CpuIdle | real | Percent of CPU time spent in idle state in past cycle. |
| CpuIOWait | real | Percent of CPU time spent waiting for I/O requests in past cycle. |
| CpuNice | real | Percent of CPU time spent running processes with positive nice values. |
| CpuSystem | real | Percent of CPU time spent running system level processes in past cycle. |
| CpuUser | real | Percent of CPU time spent running user level processes in past cycle. |
| DiskFree | real | Amount of free disk space (in GB). |
| DiskTotal | real | Total disk space (in GB). |
| FifteenMinutLoad | real | load over past 15 minutes. |
| FiveMinuteLoad | real | load over past five minutes. |
| FreeMemory | real | amount of free memory in KB. |
| FreeSwapMemory | real | amount of free swap memory in KB. |
| HostName | string | Name of the host the record came from. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| NumberOfCpu | real | Number of CPU cores running on the node. |
| OneMinuteLoad | real | load over past one minute. |
| PacketsIn | real | Packets ingest in last timeframe. |
| PacketsOut | real | Packets sent out in last timeframe. |
| ProcessesRun | real | Processes run in last timeframe. |
| ReadBytes | real | Number of bytes read. |
| ReadCount | real | Number of read operations. |
| ReadTime | real | Time spent on read operations. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SharedMemory | real | amount of sharedmemory in KB. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| TotalMemory | real | total amount of memory in KB. |
| TotalProcesses | real | Total amount of processes run on host. |
| Type | string | The name of the table |
| WriteBytes | real | Number of bytes written. |
| WriteCount | real | Number of write operations. |
| WriteTime | real | Time spent on write operations. |
