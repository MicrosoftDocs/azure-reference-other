---
title: Azure Monitor Logs reference - ADTDigitalTwinsOperation
description: Reference for ADTDigitalTwinsOperation table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# ADTDigitalTwinsOperation

 Schema for Azure Digital Twins' Digital Twin operations. The Digital Twins Operation category tracks all customer requests to manage a digital twin, including CRUD on Twins and Relationships.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Digital Twins




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationId | string | Application ID used in bearer authorization |
| CallerIpAddress | string | A masked source IP address for the event |
| Category | string | The type of resource being emitted |
| CorrelationId | string | Customer provided unique identifier for the event |
| DurationMs | string | How long it took to perform the event in milliseconds |
| Level | string | The logging severity of the event |
| Location | string | Azure region in which the Digital Twins instance is located |
| OperationName | string | The type of action being performed during the event |
| OperationVersion | string | The API Version utilized during the event |
| ParentId | string | ParentId as part of W3C's Trace Context. A request without a parent id is the root of the trace |
| RequestUri | string | The endpoint utilized during the event |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Additional details about the event |
| ResultSignature | string | Http status code of the event (if applicable) |
| ResultType | string | Outcome of the event |
| SourceSystem | string |  |
| SpanId | string | SpanId as part of W3C's Trace Context. The ID of this request in the trace |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The date and time that this event occurred, in UTC |
| TraceFlags | string | TraceFlags as part of W3C's Trace Context. Controls tracing flags such as sampling, trace level, etc. |
| TraceId | string | TraceId as part of W3C's Trace Context. The ID of the whole trace used to uniquely identify a distributed trace across systems |
| TraceState | string | TraceState as part of W3C's Trace Context. Additional vendor-specific trace identification information to span across different distributed tracing systems |
| Type | string | The name of the table |
