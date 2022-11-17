---
title: Azure Monitor Logs reference - AppServicePlatformLogs
description: Reference for AppServicePlatformLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# AppServicePlatformLogs

 Logs generated through AppService platform for your application.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- App Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActivityId | string | Activity Id to correlate events |
| ContainerId | string | Application container id |
| DeploymentId | string | Deployment ID of the application deployment |
| Exception | string | Details of the exception |
| Host | string | Host where the application is running |
| Level | string | Level of log verbosity |
| Message | string | Log message |
| OperationName | string | The name of the operation represented by this event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| StackTrace | string | Stack trace for the exception |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time when event is generated |
| Type | string | The name of the table |
