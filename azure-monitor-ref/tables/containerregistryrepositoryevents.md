---
title: Azure Monitor Logs reference - ContainerRegistryRepositoryEvents
description: Reference for ContainerRegistryRepositoryEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# ContainerRegistryRepositoryEvents

 Azure Container Registry Repository Auditing Logs

## Categories

- Containers
## Solutions

- LogManagement
## Resource types

- Container Registries




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ArtifactType | string |  |
| _BilledSize | real |  |
| CallerIpAddress | string |  |
| Category | string |  |
| CorrelationId | string |  |
| Digest | string |  |
| DurationMs | string |  |
| Identity | string |  |
| _IsBillable | string |  |
| LoginServer | string |  |
| MediaType | string |  |
| OperationName | string |  |
| Region | string |  |
| Repository | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string |  |
| ResultType | string |  |
| Size | int |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tag | string |  |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UserAgent | string |  |
| UserTenantId | string |  |
