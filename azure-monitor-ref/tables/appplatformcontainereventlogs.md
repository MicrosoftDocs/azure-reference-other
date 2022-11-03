---
title: Azure Monitor Logs reference - AppPlatformContainerEventLogs
description: Reference for AppPlatformContainerEventLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# AppPlatformContainerEventLogs

 Azure Spring Cloud container event logs of user applications.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Spring Cloud




## Columns

| Column | Type | Description |
| --- | --- | --- |
| App | string | The name of the application that emitted the container event. |
| Count | int | The count of this container event happened. |
| Deployment | string | The name of the deployment that emitted the container event. |
| Event | string | The name of container event, including: 'Backoff', 'Pulled', 'Created', 'Started', 'Unhealty' and so on. |
| FirstTimestamp | datetime | The timestamp when this container event was first seen. |
| Instance | string | The name of the instance that emitted the container event. |
| LastTimestamp | datetime | The timestamp when this container event was last seen. |
| Message | string | The detailed message of the container event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) when the log is collected by Azure Spring Cloud. |
| Type | string | The type of container event, including: 'Error', 'Warning' and 'Normal'. |
