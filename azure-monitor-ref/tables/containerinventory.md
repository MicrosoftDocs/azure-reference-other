---
title: Azure Monitor Logs reference - ContainerInventory
description: Reference for ContainerInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# ContainerInventory

 Details and current state of each container.

## Categories

- Containers
## Solutions

- ContainerInsights
- Container Monitoring Solution
## Resource types

- Kubernetes Services




## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string||
|TimeGenerated|datetime||
|Computer|string||
|ContainerID|string||
|Name|string||
|ContainerHostname|string||
|ImageID|string||
|Repository|string||
|Image|string||
|ImageTag|string||
|ContainerState|string||
|Ports|string||
|Links|string||
|ExitCode|int||
|ComposeGroup|string||
|EnvironmentVar|string||
|Command|string||
|CreatedTime|datetime||
|StartedTime|datetime||
|FinishedTime|datetime||
|Type|string||
|_ResourceId|string||
