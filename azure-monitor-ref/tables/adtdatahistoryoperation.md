---
title: Azure Monitor Logs reference - ADTDataHistoryOperation
description: Reference for ADTDataHistoryOperation table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# ADTDataHistoryOperation

 This table tracks all data history events being published to time series database connections.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Digital Twins




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationId | string | Application ID used in bearer authorization. |
| CallerIpAddress | string | A masked source IP address for the event. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| DurationMs | long | How long it took to perform the event in milliseconds. |
| Level | int | The logging severity of the event. |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API version utilized during the event. |
| ParentId | string | ParentId as part of W3C's trace context. A request without a parent id is the root of the trace. |
| Region | string | Azure region in which the Digital Twins instance is located. |
| RequestUri | string | The time series database connection's eventhub endpoint. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Additional details about the event. |
| ResultSignature | int | Http status code of the event (if applicable). |
| ResultType | string | Result of the event. For example: Success, Failure, ClientFalure, etc. |
| SourceSystem | string |  |
| SpanId | string | SpanId as part of W3C's trace context. The ID of this request in the trace. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) when the log was generated. |
| TraceFlags | string | TraceFlags as part of W3C's trace context. Controls tracing flags such as sampling, trace level, etc. |
| TraceId | string | TraceId as part of W3C's trace context. The ID of the whole trace used to uniquely identify a distributed trace across systems. |
| TraceState | string | TraceState as part of W3C's trace context. Additional vendor-specific trace identification information to span across different distributed tracing systems. |
| Type | string | The name of the table |
