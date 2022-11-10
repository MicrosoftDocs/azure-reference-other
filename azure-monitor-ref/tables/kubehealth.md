---
title: Azure Monitor Logs reference - KubeHealth
description: Reference for KubeHealth table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# KubeHealth

 

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
| Details | string |  |
| MonitorConfig | string |  |
| MonitorInstanceId | string |  |
| MonitorLabels | string |  |
| MonitorTypeId | string |  |
| NewState | string |  |
| OldState | string |  |
| ParentMonitorInstanceId | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeFirstObserved | datetime |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
