---
title: Azure Monitor Logs reference - KubeHealth
description: Reference for KubeHealth table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 8/19/2021
---

# KubeHealth

 Table that stores Health states from various health monitors for kubernetes clusters and components 

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
|Details|dynamic|Health state details|
|MonitorConfig|dynamic|Monitor configuration. This will be empty for aggregate monitors. Populated for Unit Monitors|
|MonitorInstanceId|string|Instance ID of the monitor generating the health state|
|MonitorLabels|dynamic|Monitor Labels. This may be a combination of kubernetes labels and azure monitor specific labels|
|MonitorTypeId|string|Type of the monitor. Ex;- node or cluster|
|NewState|string|New state for the monitor|
|OldState|string|Old state for the monitor|
|ParentMonitorInstanceId|string|For future [Not used]|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string|Type of agent the data was collected from. |
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TimeFirstObserved|datetime|Time the state change first was observed for this monitor|
|TimeGenerated|datetime|Date and time the record was created.|
|Type|string|The name of the table|
