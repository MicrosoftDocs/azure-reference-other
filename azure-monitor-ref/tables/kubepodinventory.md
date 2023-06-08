---
title: Azure Monitor Logs reference - KubePodInventory
description: Reference for KubePodInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
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
- Azure Arc Enabled Kubernetes
- Azure Arc Provisioned Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
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
| _IsBillable | string |  |
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
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
