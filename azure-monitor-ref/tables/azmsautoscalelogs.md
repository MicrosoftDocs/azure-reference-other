---
title: Azure Monitor Logs reference - AZMSAutoscaleLogs
description: Reference for AZMSAutoscaleLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AZMSAutoscaleLogs

 Captures auto-inflate operations done on an Event Hubs namespace.

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
| _IsBillable | string |  |
| Message | string | Informational message, which provides details about auto-inflate action. The message contains previous and current value of throughput unit for a given namespace and what triggered the inflate of the TU. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event generation time (UTC). |
| TrackingId | string | Internal ID, which is used for tracking purposes. |
| Type | string | The name of the table |
