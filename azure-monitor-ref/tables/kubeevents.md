---
title: Azure Monitor Logs reference - KubeEvents
description: Reference for KubeEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 7/20/2021
---

# KubeEvents

 Table that stores Kubernetes events 

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
|Count|real|Cumulative count of the number of occurences of a specific event [event.count] .|
|FirstSeen|datetime||
|KubeEventType|string|Type of kubernetes event [event.type]. Ex;- 'Normal' |
|LastSeen|datetime|Time event was last observed [event.lastTimestamp]|
|Message|string|Event message [event.message]|
|Name|string|Involved kubernetes object's name [event.InvolvedObject.name]. Ex;- 'autoschedulejob-158393400-gkv4g'|
|Namespace|string|Involved kubernetes object's namespace [event.InvolvedObject.namespace]. Ex;- 'kube-system'|
|ObjectKind|string|Kind of kubernetes object applicable for the event [event.InvolvedObject.kind] . Ex;- pod|
|Reason|string|Reason as seen in kubernetes event [event.reason]|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceComponent|string|Source component that generated the event [event.source.component] . Ex;- default-scheduler|
|SourceSystem|string|Type of agent the data was collected from. |
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TimeGenerated|datetime|Date and time the record was created.|
|Type|string|The name of the table|
