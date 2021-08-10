---
title: Azure Monitor Logs reference - ContainerInventory
description: Reference for ContainerInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 8/5/2021
---

# ContainerInventory

 Inventory of containers and their attributes that are monitored by the agent

## Categories

- Containers
## Solutions

- ContainerInsights
- Container Monitoring Solution
## Resource types

- Kubernetes Services
- Azure Arc enabled Kubernetes




## Columns

|Column|Type|Description|
|---|---|---|
|Command|string|entrypoint and the command executed for all running containers|
|ComposeGroup|string|Docker Compose Project name. Comes from container label : com.docker.compose.project|
|Computer|string|Computer name/Node name|
|ContainerHostname|string||
|ContainerID|string|Unique ContainerID|
|ContainerState|string|Last known state of the container|
|CreatedTime|datetime|Container creation time|
|EnvironmentVar|string|Container's environment variables|
|ExitCode|int|Container exit code|
|FinishedTime|datetime|Container termination time|
|Image|string|Container Image Name |
|ImageID|string|Container Image ID|
|ImageTag|string|Container Image Tag |
|Links|string|Container's legacy Hostconfig links|
|Name|string|Name of the container|
|Ports|string|Container's port bindings|
|Repository|string|Container's Remote repository|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string|Type of agent the data was collected from. This will be 'Containers'|
|StartedTime|datetime|Container start time|
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TimeGenerated|datetime|Date and time the record was created.|
|Type|string|The name of the table|
