---
title: Azure Monitor Logs reference - KubeMonAgentEvents
description: Reference for KubeMonAgentEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# KubeMonAgentEvents

 Events logged by Azure Monitor kubernetes agent for errors and warnings.

## Categories

- Containers
## Solutions

- AzureResources
- ContainerInsights
## Resource types

- Kubernetes Services
- Azure Arc enabled Kubernetes




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string |  |
| ClusterId | string |  |
| ClusterName | string |  |
| Computer | string |  |
| Level | string |  |
| Message | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
