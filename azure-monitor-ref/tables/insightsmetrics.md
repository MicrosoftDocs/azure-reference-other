---
title: Azure Monitor Logs reference - InsightsMetrics
description: Reference for InsightsMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# InsightsMetrics

 Performance metrics collected from virtual machines and container infrastructure.

## Categories

- Virtual Machines
- Containers
- Azure Resources
## Solutions

- ContainerInsights
- InfrastructureInsights
- Service Map
- VMInsights
## Resource types

- Virtual machine
- Virtual machine scale set
- Kubernetes Services




## Columns

|Column|Type|Description|
|---|---|---|
|AgentId|string||
|Computer|string||
|Name|string||
|Namespace|string||
|Origin|string||
|_ResourceId|string||
|SourceSystem|string||
|Tags|string||
|TimeGenerated|datetime||
|Type|string||
|Val|real||
