---
title: Azure Monitor Logs reference - ADPRequests
description: Reference for ADPRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# ADPRequests

 Requests made to the ADP service.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Autonomous Development Platform workspace




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallerIpAddress | string | IP address of the user who has performed the operation. |
| CorrelationId | string | Internal ADP correlation ID used in support scenarios. |
| DurationMs | int | The duration of the operation in milliseconds. |
| HttpStatusCode | int | The HTTP response status code of the corresponding REST call. |
| Location | string | The location (region) of the resource. |
| OperationName | string | The operation associated with the log record. |
| OperationVersion | string | The API version against which the operation was performed. |
| Properties | dynamic | Additional properties related to the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Success | bool | Whether the request was successful or not. Note that long-running asynchronous operations might fail even when the request is successful. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log record was generated. |
| TraceContext | dynamic | W3C Trace Context information used for event correlation. |
| Type | string | The name of the table |
| Uri | string | The URI of the request. |
