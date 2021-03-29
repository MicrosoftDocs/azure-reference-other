---
title: Azure Monitor Logs reference - KubeNodeInventory
description: Reference for KubeNodeInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 3/29/2021
---

# KubeNodeInventory

 Table that stores kubernetes cluster's node information

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
|ClusterId|string|ID of the kubernetes cluster from which the event was sourced|
|ClusterName|string|ID of the kubernetes cluster from which the event was sourced|
|Computer|string|Computer/node name in the cluster for which the event applies. If not, computer/node name of sourcing computer|
|CreationTimeStamp|datetime|Node created time|
|DockerVersion|string|Container runtime version|
|KubeletVersion|string|Version of Kubelet in the node|
|KubeProxyVersion|string|Version of KubePxoxy in the node|
|KubernetesProviderID|string|Provider ID for Kubernetes|
|Labels|string|Kubernetes Node Labels|
|LastTransitionTimeReady|datetime|Last transition to/from ready condition for the node (no matter ready is true/false)|
|OperatingSystem|string|Nodes host OS Image|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string|Type of agent the data was collected from. |
|Status|string|Comma seperated list of node's status.conditions.type for conditions.status that are true|
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TimeGenerated|datetime|Date and time the record was created.|
|Type|string|The name of the table|
