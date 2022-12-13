---
title: Azure Monitor Logs reference - AppPlatformBuildLogs
description: Reference for AppPlatformBuildLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
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
| BuildLog | string | The build log for each build stages. |
| ContainerName | string | The name of the container that emitted the log. |
| PodName | string | The name of the pod that emitted the log. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) when the log is collected by Azure Spring Cloud. |
| Type | string | The name of the table |
