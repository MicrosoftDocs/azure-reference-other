---
title: Azure Monitor Logs reference - KubeMonAgentEvents
description: Reference for KubeMonAgentEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# KubeMonAgentEvents

 Events logged by Azure Monitor kubernetes agent for errors and warnings.

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
|Computer|string||
|TimeGenerated|datetime||
|Category|string||
|Level|string||
|ClusterId|string||
|ClusterName|string||
|Message|string||
|Tags|dynamic||
|Type|string||
|_ResourceId|string||
