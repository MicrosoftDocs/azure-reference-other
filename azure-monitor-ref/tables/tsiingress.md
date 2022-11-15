---
title: Azure Monitor Logs reference - TSIIngress
description: Reference for TSIIngress table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# TSIIngress

 The Ingress category tracks errors that occur in the ingress pipeline. This category includes errors that occur when receiving events (such as failures to connect to an Event Source) and processing events (such as errors when parsing an event payload).

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Time Series Insights Environments




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | Category of the log event. |
| CorrelationId | string | The correlation ID of the request. |
| ErrorCode | string | The code associated with the error |
| EventSourceProperties | dynamic | A collection of properties specific to your event source. Contains details such as the consumer group and the access key name. |
| EventSourceType | string | The type of event source. It could either be Event hub or IoT hub. |
| Level | string | The severity level of the event. |
| Location | string | The location of the resource. |
| Message | string | The message associated with the error. Includes details on what went wrong and how to mitigate the error. |
| OperationName | string | Operation name of the event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Description of the result of the operation, such as 'Received forbidden error'. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time (UTC) at which this event is generated. |
| Type | string | The name of the table |
