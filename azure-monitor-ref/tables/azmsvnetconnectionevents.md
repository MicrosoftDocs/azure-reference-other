---
title: Azure Monitor Logs reference - AZMSVnetConnectionEvents
description: Reference for AZMSVnetConnectionEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AZMSVnetConnectionEvents

 Captures all virtual network and IP filtering logs for Azure Event Hubs and Azure Service Bus. These would only be emitted if namespace allows access from selected networks or from specific IP address (IP Filter rules).

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Event Hubs
- Service Bus




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Action | string | Action done by the service when evaluating connection requests. Supported actions are accept connection and deny connection. |
| AddressIp | string | IP address of a client connecting to the Event Hubs or Service Bus service. |
| _BilledSize | real |  |
| Count | int | Number of occurrences for the given action. |
| _IsBillable | string |  |
| Message | string | Provides a reason why the action was done. |
| NamespaceName | string | Name of Event Hubs or Service Bus namespace. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event generation time (UTC). |
| Type | string | The name of the table |
