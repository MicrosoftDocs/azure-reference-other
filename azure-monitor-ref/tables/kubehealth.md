---
title: Azure Monitor Logs reference - KubeHealth
description: Reference for KubeHealth table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# KubeHealth

 

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
| Details | string |  |
| _IsBillable | string |  |
| MonitorConfig | string |  |
| MonitorInstanceId | string |  |
| MonitorLabels | string |  |
| MonitorTypeId | string |  |
| NewState | string |  |
| OldState | string |  |
| ParentMonitorInstanceId | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeFirstObserved | datetime |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
