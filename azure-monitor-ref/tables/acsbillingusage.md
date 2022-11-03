---
title: Azure Monitor Logs reference - ACSBillingUsage
description: Reference for ACSBillingUsage table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# ACSBillingUsage

 Usage records across all modes of Communication Services.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Communication Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | The log category of the event. Category is the granularity at which you can enable or disable logs on a particular resource. The properties that appear within the properties blob of an event are the same within a particular log category and resource type. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| EndTime | datetime | The time when resource consumption ended. Optional, as some events are instant by nature. |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API-version associated with the operation, if the operationName was performed using an API. If there is no API that corresponds to this operation, the version represents the version of that operation in case the properties associated with the operation change in the future. |
| Quantity | real | The amount of usage in terms of the specified unit. |
| RecordId | string | The unique id for a given usage record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| StartTime | datetime | Time when the resource consumption started. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UnitType | string | The unit in which the type of usage is measured |
| UsageType | string | The type of resource being consumed. |
| UserIdA | string | User id consuming the resource. |
| UserIdB | string | User id consuming the resource for consumables involving two users. |
