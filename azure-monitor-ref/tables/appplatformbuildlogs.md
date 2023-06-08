---
title: Azure Monitor Logs reference - AppPlatformBuildLogs
description: Reference for AppPlatformBuildLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AppPlatformBuildLogs

 Azure Spring Cloud build logs of user source codes.

## Solutions

- LogManagement
## Resource types

- Azure Spring Cloud




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| BuildLog | string | The build log for each build stages. |
| ContainerName | string | The name of the container that emitted the log. |
| _IsBillable | string |  |
| PodName | string | The name of the pod that emitted the log. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) when the log is collected by Azure Spring Cloud. |
| Type | string | The name of the table |
