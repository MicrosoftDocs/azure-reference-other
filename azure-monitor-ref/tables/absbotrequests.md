---
title: Azure Monitor Logs reference - ABSBotRequests
description: Reference for ABSBotRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# ABSBotRequests

 Logs of requests made by Azure Bot Service onbehalf of a bot such as requests from channel to bot and to other dependencies.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Bot Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| BotId | string | Name of the bot or the bot handle. |
| Category | string | Classification of the log. |
| Channel | string | Name of the Channel generating the log such as Direct Line, MS Teams, Facebook, etc. |
| CorrelationId | string | The ID for the correlated events. Can be used to identify correlated events between multiple tables. |
| DurationMs | real | Duration of the request. |
| _IsBillable | string |  |
| Level | string | log level of message such as Information, Warning, Error, etc. |
| Location | string | Location of the service sending the log (Azure region name e.g. West US). |
| OperationName | string | The operation associated with the log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultCode | int | HTTP request response code. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
