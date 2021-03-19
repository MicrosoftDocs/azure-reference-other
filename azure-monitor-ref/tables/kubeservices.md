---
title: Azure Monitor Logs reference - KubeServices
description: Reference for KubeServices table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 3/19/2021
---

# KubeServices

 Table that stores Kubernetes services information 

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
|ClusterIp|string|Cluster IP address of the service|
|ClusterName|string|ID of the kubernetes cluster from which the event was sourced|
|Namespace|string|Kuberneets namespace for the service|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SelectorLabels|string|Selector labels for label based services|
|ServiceName|string|Kubernetes Service name|
|ServiceType|string|Kubernetes Service type [ClusterIP/NodePort/LoadBalancer/ExternalName]|
|SourceSystem|string|Type of agent the data was collected from. |
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TimeGenerated|datetime|Date and time the record was created.|
|Type|string|The name of the table|
