---
title: Azure Monitor Logs reference - KubeEvents
description: Reference for KubeEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# KubeEvents

 Kubernetes events and their properties.

## Categories

- Containers
## Solutions

- ContainerInsights
## Resource types

- Kubernetes Services




## Columns

|Column|Type|Description|
|---|---|---|
|ClusterId|string||
|ClusterName|string||
|Computer|string||
|Count|real||
|FirstSeen|datetime||
|KubeEventType|string||
|LastSeen|datetime||
|Message|string||
|Name|string||
|Namespace|string||
|ObjectKind|string||
|Reason|string||
|_ResourceId|string||
|SourceComponent|string||
|SourceSystem|string||
|TimeGenerated|datetime||
|Type|string||
