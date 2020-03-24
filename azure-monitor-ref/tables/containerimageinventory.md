---
title: Azure Monitor Logs reference - ContainerImageInventory
description: Reference for ContainerImageInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# ContainerImageInventory

 

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
|ImageID|string||
|Repository|string||
|Image|string||
|ImageTag|string||
|ImageSize|string||
|VirtualSize|string||
|Running|int||
|Stopped|int||
|Failed|int||
|Paused|int||
|TotalContainer|long||
|Type|string||
|_ResourceId|string||
