---
title: Azure Monitor Logs reference - KubeEvents
description: Reference for KubeEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/16/2023
---

# KubeEvents

 Kubernetes events and their properties.

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
| ClusterId | string |  |
| ClusterName | string |  |
| Computer | string |  |
| Count | real |  |
| FirstSeen | datetime |  |
| KubeEventType | string |  |
| LastSeen | datetime |  |
| Message | string |  |
| Name | string |  |
| Namespace | string |  |
| ObjectKind | string |  |
| Reason | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceComponent | string |  |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
