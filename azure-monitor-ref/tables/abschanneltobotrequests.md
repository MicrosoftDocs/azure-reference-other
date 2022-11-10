---
title: Azure Monitor Logs reference - ABSChannelToBotRequests
description: Reference for ABSChannelToBotRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# ABSChannelToBotRequests

 All logs of requests from Azure Bot Service channels services to bots.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| BotId | string | Name of the bot or the bot handle. |
| Category | string | Classification of the log. |
| Channel | string | Name of the Channel making generating the log (e.g. DirectLine, Facebook, etc.). |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| DurationMs | real | Duration of a request. |
| Level | string | log level of message (Information, Warning, Error, etc.). |
| Location | string | Location of the service sending the log (Azure region name e.g. West US). |
| OperationName | string | The operation associated with log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultCode | int | HTTP request response code. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
