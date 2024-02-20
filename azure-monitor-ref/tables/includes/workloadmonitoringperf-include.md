---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: WorkloadMonitoringPerf
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Computer | string |   |
| CounterName | string |   |
| InstanceName | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsSystemDisk | string |   |
| LogicalDisk | string |   |
| MemoryInstance | string |   |
| NetworkAdapter | string |   |
| ObjectName | string |   |
| PerfCounterValue | real |   |
| PhysicalDisk | string |   |
| ProcessorInformation | string |   |
| ProcessorInstance | string |   |
| SecureChannel | string |   |
| ServiceName | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
