---
title: Azure Monitor Logs reference - KubeEvents
description: Reference for KubeEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
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
|SourceSystem|string||
|TimeGenerated|datetime||
|Computer|string||
|ObjectKind|string||
|Namespace|string||
|Name|string||
|Reason|string||
|Message|string||
|KubeEventType|string||
|SourceComponent|string||
|FirstSeen|datetime||
|LastSeen|datetime||
|Count|real||
|ClusterName|string||
|ClusterId|string||
|Type|string||
|_ResourceId|string||
