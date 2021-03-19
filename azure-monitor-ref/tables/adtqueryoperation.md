---
title: Azure Monitor Logs reference - ADTQueryOperation
description: Reference for ADTQueryOperation table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 3/19/2021
---

# ADTQueryOperation

 Schema for Azure Digital Twins' Query operations. The Query Operation category tracks all customer requests to query their digital twins instance.

## Solutions

- LogManagement
## Resource types

- Azure Digital Twins




## Columns

|Column|Type|Description|
|---|---|---|
|Caller IP Address|string|IP address of the requester|
|Category|string|Category of the log event|
|Correlation ID|string|Correlation ID of the operation|
|DurationMs|string|Duration of the operation in milliseconds|
|Level|string|Level of severity of the event|
|Location|string|Azure region in which the Iot Hub is located|
|OperationName|string|Operation name of the event|
|OperationVersion|string|Operation version of the event|
|RequestUri|string|The URI of the request.|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ResultDescription|string|Result description of the event, typically elaborates on the error|
|ResultSignature|string|Result signature of the event, typically the status code of the result|
|ResultType|string|Result type of the event, typically empty unless it's an error|
|SourceSystem|string||
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TenantId|string||
|TimeGenerated|datetime|Time at which this event is generated|
|Type|string|The name of the table|
