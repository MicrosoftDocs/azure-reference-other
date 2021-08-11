---
title: Azure Monitor Logs reference - KubePodInventory
description: Reference for KubePodInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 8/11/2021
---

# KubePodInventory

 Table that stores kubernetes cluster's Pod & container information

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
|Computer|string|Computer/node name in the cluster that has this pod/container. Unscheduled pods will have this as empty.|
|ContainerCreationTimeStamp|datetime|Container creation time|
|ContainerID|string|Container's ID|
|ContainerLastStatus|string|Container's last observed last status|
|ContainerName|string|Container name. This is in poduid/containername format.|
|ContainerRestartCount|int|Restart count for the container|
|ContainerStartTime|datetime|Time container started.|
|ContainerStatus|string|Container's last observered current state [container.state]|
|ContainerStatusReason|string|Reason if any for container's status.|
|ControllerKind|string|Container/Pod's controller kind. Ex;- ReplicaSet |
|ControllerName|string|Container/Pod's controller Name. Ex;- kubernetes-dashboard-9f5bf9974 |
|InstanceName|string|Not used currently[for future use]|
|Name|string|Kubernetes Pod Name|
|Namespace|string|Kubernetes Namespace for the pod/container|
|PodCreationTimeStamp|datetime|Pod creation time|
|PodIp|string|Pod's IP Address|
|PodLabel|string|Pod Labels|
|PodRestartCount|int|Restart count for the pod. [Sum of all restarts of all containers in the pod]|
|PodStartTime|datetime|Pod's start time (for started pods)|
|PodStatus|string|Last observed Pod Status [pod.status.phase]|
|PodUid|string|Unique ID of the pod|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ServiceName|string|Kubernetes Service the pod belongs to (if any)|
|SourceSystem|string|Type of agent the data was collected from. |
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TimeGenerated|datetime|Date and time the record was created.|
|Type|string|The name of the table|
