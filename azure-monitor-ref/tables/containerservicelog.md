---
title: Azure Monitor Logs reference - ContainerServiceLog
description: Reference for ContainerServiceLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/9/2023
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
- Azure Arc Enabled Kubernetes
- Azure Arc Provisioned Clusters




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
