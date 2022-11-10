---
title: Azure Monitor Logs reference - IoTHubDistributedTracing
description: Reference for IoTHubDistributedTracing table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# IoTHubDistributedTracing

 The distributed tracing category tracks the trace-id and span-id for messages that carry the trace context header. To fully enable these logs, client-side code must be updated by following https://aka.ms/iottracing

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- IoT Hub




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallerLocalTimeUtc | datetime | Creation time of the message as reported by the device local clock |
| Category | string | Category of the log event |
| DependencyType | string | For outgoing requests (dependencies), describes type of the dependency |
| DurationMs | int | Duration of the operation in milliseconds |
| EventKind | string | Kind of the event |
| InstanceId | string | Name of the instance that processed request |
| IsRoutingEnabled | bool | Either true or false, indicates whether or not message routing is enabled in the IoT Hub |
| Level | string | Level of severity of the event |
| Location | string | Azure region in which the Iot Hub is located |
| MessageSize | int | The size of the message in bytes |
| OperationName | string | Operation name of the event |
| ParentId | string | Unique identifier of current span within trace (16 hex characters). A request without a parent id is the root of the trace. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceSubName | string | Name of sub-component that reports this message |
| ResultDescription | string | Result description of the event, typically elaborates on the error |
| ResultSignature | int | The status code of the event |
| ResultType | string | Result type of the event, typically empty unless it's an error |
| SourceSystem | string |  |
| SpanId | string | Unique identifier of current span within trace (16 hex characters) |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time at which this event is generated and logged |
| TraceFlags | int | A bit field for controlling tracing options. For example, sampling and trace level. |
| TraceId | string | Globally unique identifier of the trace (32 hex characters) |
| Type | string | The name of the table |
| Uri | string | Absolute request URI |
