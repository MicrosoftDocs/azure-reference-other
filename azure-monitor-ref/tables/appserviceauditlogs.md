---
title: Azure Monitor Logs reference - AppServiceAuditLogs
description: Reference for AppServiceAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# AppServiceAuditLogs

 Logs generated when publishing users successfully log on via one of the App Service publishing protocols.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- App Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | Log category name |
| OperationName | string | Name of the operation |
| Protocol | string | Authentication protocol |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time when event is generated |
| Type | string | The name of the table |
| User | string | Username used for publishing access |
| UserAddress | string | Client IP addres of the publishing user |
| UserDisplayName | string | Email address of a user in case publishing was authorized via AAD authentication |
