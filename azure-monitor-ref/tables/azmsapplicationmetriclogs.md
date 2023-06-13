---
title: Azure Monitor Logs reference - AZMSApplicationMetricLogs
description: Reference for AZMSApplicationMetricLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AZMSApplicationMetricLogs

 Captures application metrics(incoming/outgoing, successful/failed, etc. message delivery) for Azure Event Hubs and Azure Service Bus.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Service Bus




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActivityId | string | Internal ID, used to identify the specified activity. |
| AuthId | string | Authentication ID configured for Event Hub. |
| AuthType | string | Type of authentication (Azure Active Directory or SAS Policy). |
| _BilledSize | real |  |
| _IsBillable | string |  |
| OperationName | string | Operation performed on Event Hub (ConsumerLag, ActiveConnection, IncomingMessages, Etc.). |
| Outcome | string | Result of operation. Possible values: Success/Failure. |
| Properties | dynamic | Metadata that are specific to the operation. |
| Protocol | string | Protocol used to perform the operation. Possible value: AMQP, Kafka, and SBMP. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event start time (UTC). |
| Type | string | The name of the table |
| Value | int | Value with respect to performed operation. |
