---
title: Azure Monitor Logs reference - KubeNodeInventory
description: Reference for KubeNodeInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# KubeNodeInventory

 Details for nodes that are part of kubernetes cluster.

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
|ClusterName|string||
|ClusterId|string||
|LastTransitionTimeReady|datetime||
|Labels|string||
|Status|string||
|KubeletVersion|string||
|KubeProxyVersion|string||
|CreationTimeStamp|datetime||
|KubernetesProviderID|string||
|OperatingSystem|string||
|DockerVersion|string||
|Type|string||
|_ResourceId|string||
