---
title: Azure Monitor Logs reference - AppServiceAuditLogs
description: Reference for AppServiceAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
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
| _BilledSize | real |  |
| Category | string | Log category name |
| _IsBillable | string |  |
| OperationName | string | Name of the operation |
| Protocol | string | Authentication protocol |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time when event is generated |
| Type | string | The name of the table |
| User | string | Username used for publishing access |
| UserAddress | string | Client IP addres of the publishing user |
| UserDisplayName | string | Email address of a user in case publishing was authorized via AAD authentication |
