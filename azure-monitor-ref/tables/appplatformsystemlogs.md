---
title: Azure Monitor Logs reference - AppPlatformSystemLogs
description: Reference for AppPlatformSystemLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# AppPlatformSystemLogs

 Azure Spring Cloud System Logs.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Spring Cloud




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | Log Category |
| InstanceName | string | The instance name that emitted the log |
| Level | string | The level of the log |
| Log | string | The log of the log |
| Logger | string | The logger of the log |
| LogType | string | The type of the log |
| OperationName | string | The name of the operation represented by this event |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ServiceName | string | The service name that emitted the log |
| SourceSystem | string |  |
| Stack | string | The stack of the log |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| Thread | string | The thread of the log |
| TimeGenerated | datetime | The timestamp (UTC) when the log is collected by Azure Spring Cloud |
| Type | string | The name of the table |
