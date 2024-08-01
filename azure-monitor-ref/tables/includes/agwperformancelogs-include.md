---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AGWPerformanceLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| FailedRequestCount | int | Number of failed requests. |
| HealthyHostCount | int | Number of healthy hosts in the backend pool. |
| InstanceId | string | Application Gateway instance for which performance data is being generated. For a multiple-instance application gateway, there is one row per instance. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Latency | int | Average latency (in milliseconds) of requests from the instance to the back end that serves the requests. |
| OperationName | string | Name of the operation. |
| RequestCount | int | Number of requests served. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| Throughput | int | Average throughput since the last log, measured in bytes per second. |
| TimeGenerated | datetime | Time (UTC) when the log was created. |
| Type | string | The name of the table |
| UnHealthyHostCount | int | Number of unhealthy hosts in the backend pool. |
