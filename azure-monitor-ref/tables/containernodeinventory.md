---
title: Azure Monitor Logs reference - ContainerNodeInventory
description: Reference for ContainerNodeInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 8/11/2021
---

# ContainerNodeInventory

 Table that stores Container host/node information

## Categories

- Containers
## Solutions

- ContainerInsights
## Resource types

- Kubernetes Services
- Azure Arc enabled Kubernetes




## Columns

|Column|Type|Description|
|---|---|---|
|Computer|string|Computer/node name in the cluster for which the event applies. If not, computer/node name of sourcing computer|
|DockerVersion|string|Container runtime version|
|OperatingSystem|string|Nodes host OS Image|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string|Type of agent the data was collected from. |
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TimeGenerated|datetime|Date and time the record was created.|
|Type|string|The name of the table|
