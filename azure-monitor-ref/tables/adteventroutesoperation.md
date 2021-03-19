---
title: Azure Monitor Logs reference - ADTEventRoutesOperation
description: Reference for ADTEventRoutesOperation table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 3/19/2021
---

# ADTEventRoutesOperation

 Schema for Azure Digital Twins' Event Routes operations. The Event Routes Operation category tracks all events being published to endpoints, which are other Azure services.

## Solutions

- LogManagement
## Resource types

- Azure Digital Twins




## Columns

|Column|Type|Description|
|---|---|---|
|Category|string|Category of the log event|
|Correlation ID|string|Correlation ID of the operation|
|Endpoint Name|string|Name of the endpoint the event is being routed to|
|Level|string|Level of severity of the event|
|Location|string|Azure region in which the Iot Hub is located|
|OperationName|string|Operation name of the event|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ResultDescription|string|Result description of the event, typically elaborates on the error|
|SourceSystem|string||
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TenantId|string||
|TimeGenerated|datetime|Time at which this event is generated|
|Type|string|The name of the table|
