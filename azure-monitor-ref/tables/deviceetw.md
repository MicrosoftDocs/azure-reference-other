---
title: Azure Monitor Logs reference - DeviceEtw
description: Reference for DeviceEtw table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/10/2023
---

# DeviceEtw

 

## Categories

- Workloads
## Solutions

- Surface Hub




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActivityId | string |  |
| appName | string |  |
| _BilledSize | real | The record size in bytes |
| Computer | string |  |
| DeviceType | string |  |
| EventId | int |  |
| EventName | string |  |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| period | int |  |
| ProcessId | string |  |
| ProviderId | string |  |
| SerialNumber | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| status | int |  |
| tags | string |  |
| ThreadId | int |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| type | int |  |
| wakeEnabled | bool |  |
