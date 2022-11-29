---
title: Azure Monitor Logs reference - KubePodInventory
description: Reference for KubePodInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# KubePodInventory

 Kubernetes pods and their properties

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
| ClusterId | string |  |
| ClusterName | string |  |
| Computer | string |  |
| ContainerCreationTimeStamp | datetime |  |
| ContainerID | string |  |
| ContainerLastStatus | string |  |
| ContainerName | string |  |
| ContainerRestartCount | int |  |
| ContainerStartTime | datetime |  |
| ContainerStatus | string |  |
| ContainerStatusReason | string |  |
| ControllerKind | string |  |
| ControllerName | string |  |
| InstanceName | string |  |
| Name | string |  |
| Namespace | string |  |
| PodCreationTimeStamp | datetime |  |
| PodIp | string |  |
| PodLabel | string |  |
| PodRestartCount | int |  |
| PodStartTime | datetime |  |
| PodStatus | string |  |
| PodUid | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ServiceName | string |  |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
