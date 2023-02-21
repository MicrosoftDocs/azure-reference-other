---
title: Azure Monitor Logs reference - ContainerImageInventory
description: Reference for ContainerImageInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/16/2023
---

# ContainerImageInventory

 

## Categories

- Containers
## Solutions

- AzureResources
- ContainerInsights
- Container Monitoring Solution
## Resource types

- Kubernetes Services
- Azure Arc Enabled Kubernetes
- Azure Arc Provisioned Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Computer | string |  |
| Failed | int |  |
| Image | string |  |
| ImageID | string |  |
| ImageSize | string |  |
| ImageTag | string |  |
| Paused | int |  |
| Repository | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Running | int |  |
| SourceSystem | string |  |
| Stopped | int |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| TotalContainer | long |  |
| Type | string | The name of the table |
| VirtualSize | string |  |
