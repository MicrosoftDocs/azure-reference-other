---
title: Azure Monitor Logs reference - AZMSKafkaCoordinatorLogs
description: Reference for AZMSKafkaCoordinatorLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AZMSKafkaCoordinatorLogs

 Captures kafka coordinator operations related to Event Hubs.

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
| ClientId | string | The client ID. |
| _IsBillable | string |  |
| Message | string | The Informational or warning message, which provides detailes about actions done during the group coordiantion. |
| NamespaceName | string | The namespace name. |
| Operation | string | The name of operation that done during the group coordination. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| RequestId | string | The request ID, which is used for tracking purposes. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event generation time(UTC). |
| Type | string | The name of the table |
