---
title: Azure Monitor Logs reference - WorkloadMonitoringPerf
description: Reference for WorkloadMonitoringPerf table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# WorkloadMonitoringPerf

 

## Categories

- Workloads
## Solutions

- InfrastructureInsights




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Computer | string |  |
| CounterName | string |  |
| InstanceName | string |  |
| _IsBillable | string |  |
| IsSystemDisk | string |  |
| LogicalDisk | string |  |
| MemoryInstance | string |  |
| NetworkAdapter | string |  |
| ObjectName | string |  |
| PerfCounterValue | real |  |
| PhysicalDisk | string |  |
| ProcessorInformation | string |  |
| ProcessorInstance | string |  |
| SecureChannel | string |  |
| ServiceName | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
