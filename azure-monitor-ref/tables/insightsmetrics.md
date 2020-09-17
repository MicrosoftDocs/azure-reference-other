---
title: Azure Monitor Logs reference - InsightsMetrics
description: Reference for InsightsMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/17/2020
---

# InsightsMetrics

 Table that stores metrics. 'Perf' table also stores many metrics and over time they all will converge to InsightsMetrics for Azure Monitor Solutions 

## Categories

- Azure Resources
- Containers
- Virtual Machines
## Solutions

- Service Map
- Azure Monitor for VMs
- ContainerInsights
- InfrastructureInsights
## Resource types

- Kubernetes Services
- IoT Hub
- Virtual machines
- Virtual Machine Scale Sets




## Columns

|Column|Type|Description|
|---|---|---|
|AgentId|string|Unique ID of the agent that sourced the metric instance|
|Computer|string|Computer name/Node name that sourced the metric instance|
|Name|string|Name of the metric|
|Namespace|string|Name space/Category of the metric. Ex;- 'container.azm.ms/disk' |
|Origin|string|Source of the metric. Ex;- 'container.azm.ms/telegraf'|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string|Type of agent the data was collected from. Ex;- 'Insights' |
|Tags|string|Dimensions of the metric in json|
|TimeGenerated|datetime|Date and time the record was created.|
|Type|string|The name of the table|
|Val|real|Value of the metric|
