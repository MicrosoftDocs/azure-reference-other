---
title: Azure Monitor Logs reference - ContainerInventory
description: Reference for ContainerInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# ContainerInventory

 Details and current state of each container.

## Categories

- Containers
## Solutions

- AzureResources
- ContainerInsights
- Container Monitoring Solution
## Resource types

- Kubernetes Services
- Azure Arc enabled Kubernetes




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Command | string |  |
| ComposeGroup | string |  |
| Computer | string |  |
| ContainerHostname | string |  |
| ContainerID | string |  |
| ContainerState | string |  |
| CreatedTime | datetime |  |
| EnvironmentVar | string |  |
| ExitCode | int |  |
| FinishedTime | datetime |  |
| Image | string |  |
| ImageID | string |  |
| ImageTag | string |  |
| Links | string |  |
| Name | string |  |
| Ports | string |  |
| Repository | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| StartedTime | datetime |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
