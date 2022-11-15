---
title: Azure Monitor Logs reference - ContainerRegistryRepositoryEvents
description: Reference for ContainerRegistryRepositoryEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
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
| CallerIpAddress | string |  |
| Category | string |  |
| CorrelationId | string |  |
| Digest | string |  |
| DurationMs | string |  |
| Identity | string |  |
| LoginServer | string |  |
| MediaType | string |  |
| OperationName | string |  |
| Region | string |  |
| Repository | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string |  |
| ResultType | string |  |
| Size | int |  |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tag | string |  |
| TenantId | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UserAgent | string |  |
| UserTenantId | string |  |
