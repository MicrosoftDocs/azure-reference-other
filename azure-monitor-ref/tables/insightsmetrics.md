---
title: Azure Monitor Logs reference - InsightsMetrics
description: Reference for InsightsMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
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
|SourceSystem|string||
|TimeGenerated|datetime||
|Computer|string||
|Origin|string||
|Namespace|string||
|Name|string||
|Val|real||
|Tags|string||
|AgentId|string||
|Type|string||
|_ResourceId|string||
