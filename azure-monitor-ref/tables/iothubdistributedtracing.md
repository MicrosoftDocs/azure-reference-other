---
title: Azure Monitor Logs reference - IoTHubDistributedTracing
description: Reference for IoTHubDistributedTracing table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# IoTHubDistributedTracing

 The distributed tracing category tracks the trace-id and span-id for messages that carry the trace context header. To fully enable these logs, client-side code must be updated by following https://aka.ms/iottracing

## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|TimeGenerated|datetime|Time at which this event is generated and logged|
|OperationName|string|Operation name of the event|
|Level|string|Level of severity of the event|
|Location|string|Azure region in which the Iot Hub is located|
|Category|string|Category of the log event|
|ResultType|string|Result type of the event, typically empty unless it's an error|
|ResultSignature|int|The status code of the event|
|ResultDescription|string|Result description of the event, typically elaborates on the error|
|DurationMs|int|Duration of the operation in milliseconds|
|TraceId|string|Globally unique identifier of the trace (32 hex characters)|
|SpanId|string|Unique identifier of current span within trace (16 hex characters)|
|ParentId|string|Unique identifier of current span within trace (16 hex characters). A request without a parent id is the root of the trace.|
|TraceFlags|int|A bit field for controlling tracing options. For example, sampling and trace level.|
|EventKind|string|Kind of the event|
|InstanceId|string|Name of the instance that processed request|
|Uri|string|Absolute request URI|
|ResourceSubName|string|Name of sub-component that reports this message|
|DependencyType|string|For outgoing requests (dependencies), describes type of the dependency|
|MessageSize|int|The size of the message in bytes|
|CallerLocalTimeUtc|datetime|Creation time of the message as reported by the device local clock|
|IsRoutingEnabled|bool|Either true or false, indicates whether or not message routing is enabled in the IoT Hub|
|SourceSystem|string||
|Type|string||
|_ResourceId|string||
