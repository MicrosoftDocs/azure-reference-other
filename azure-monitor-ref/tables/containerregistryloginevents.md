---
title: Azure Monitor Logs reference - ContainerRegistryLoginEvents
description: Reference for ContainerRegistryLoginEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# ContainerRegistryLoginEvents

 Azure Container Registry Login Auditing Logs

## Categories

- Containers
## Solutions

- LogManagement
## Resource types

- Container Registries




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| CallerIpAddress | string |  |
| Category | string |  |
| CorrelationId | string |  |
| DurationMs | string |  |
| Identity | string |  |
| _IsBillable | string |  |
| JwtId | string |  |
| LoginServer | string |  |
| OperationName | string |  |
| Region | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string |  |
| ResultType | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UserAgent | string |  |
