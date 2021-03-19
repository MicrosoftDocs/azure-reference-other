---
title: Azure Monitor Logs reference - KubeMonAgentEvents
description: Reference for KubeMonAgentEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 3/19/2021
---

# KubeMonAgentEvents

 Table that stores events from the Kubernetes cluster monitoring agent [Azure Monitor Agent]

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
|Category|string|Category of the event. Ex;- container.azm.ms/promscraping, container.azm.ms/configmap|
|ClusterId|string|ID of the kubernetes cluster from which the event was sourced|
|ClusterName|string|ID of the kubernetes cluster from which the event was sourced|
|Computer|string|Computer/node name in the cluster for which the event applies. If not, computer/node name of sourcing computer|
|Level|string|Event level for the event. [Error, Warning, Info]|
|Message|string|Event message.|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string|Type of agent the data was collected from. |
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|Tags|dynamic|Dimensions/properties for the event|
|TimeGenerated|datetime|Date and time the record was created.|
|Type|string|The name of the table|
