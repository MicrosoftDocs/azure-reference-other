---
title: Azure Monitor Logs reference - AZMSKafkaUserErrorLogs
description: Reference for AZMSKafkaUserErrorLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AZMSKafkaUserErrorLogs

 Captures information about kafka APIs called on Event Hubs.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Event Hubs




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| EventhubName | string | Name of Event Hub. |
| _IsBillable | string |  |
| Message | string | The informational message, which provides details about an error. |
| NamespaceName | string | Name of Event Hubs namespace. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event start time (UTC). |
| TrackingId | string | The tracking ID, which is used for tracking purposes. |
| Type | string | The name of the table |
