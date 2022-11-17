---
title: Azure Monitor Logs reference - ContainerRegistryLoginEvents
description: Reference for ContainerRegistryLoginEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
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
| CallerIpAddress | string |  |
| Category | string |  |
| CorrelationId | string |  |
| DurationMs | string |  |
| Identity | string |  |
| JwtId | string |  |
| LoginServer | string |  |
| OperationName | string |  |
| Region | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string |  |
| ResultType | string |  |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UserAgent | string |  |
