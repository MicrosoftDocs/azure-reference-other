---
title: Azure Monitor Logs reference - AZMSOperationalLogs
description: Reference for AZMSOperationalLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AZMSOperationalLogs

 Captures all management operations that are performed on the Azure Event Hubs/Azure Service Bus namespace and its entities.

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
| _BilledSize | real |  |
| Caller | string | The caller of operation (the Azure portal or management client). |
| EventName | string | The name of management operation which is executed within Service Bus. |
| EventProperties | dynamic | The operation properties. |
| _IsBillable | string |  |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| Status | string | The operation status. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The log generation time (UTC). |
| Type | string | The name of the table |
