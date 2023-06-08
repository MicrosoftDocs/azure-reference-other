---
title: Azure Monitor Logs reference - ServiceFabricOperationalEvent
description: Reference for ServiceFabricOperationalEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# ServiceFabricOperationalEvent

 

## Categories

- Azure Resources
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationName | string |  |
| ApplicationTypeName | string |  |
| ApplicationTypeVersion | string |  |
| AzureDeploymentID | string |  |
| _BilledSize | real |  |
| ChannelName | string |  |
| Computer | string |  |
| EventId | int |  |
| EventMessage | string |  |
| EventSourceName | string |  |
| _IsBillable | string |  |
| KeywordName | string |  |
| Level | string |  |
| OpcodeName | string |  |
| PartitionId | string |  |
| Pid | int |  |
| ProviderGuid | string |  |
| Role | string |  |
| ServiceName | string |  |
| ServiceTypeName | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TaskName | string |  |
| Tid | int |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UpgradeDomains | string |  |
