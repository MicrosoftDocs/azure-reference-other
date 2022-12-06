---
title: Azure Monitor Logs reference - ContainerServiceLog
description: Reference for ContainerServiceLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# ContainerServiceLog

 

## Categories

- Containers
## Solutions

- AzureResources
- ContainerInsights
- Container Monitoring Solution
## Resource types

- Kubernetes Services
- Azure Arc enabled Kubernetes




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Command | string |  |
| Computer | string |  |
| ContainerID | string |  |
| Image | string |  |
| ImageTag | string |  |
| Repository | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| TimeOfCommand | datetime |  |
| Type | string | The name of the table |
