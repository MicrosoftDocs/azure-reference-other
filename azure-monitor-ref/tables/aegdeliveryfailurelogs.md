---
title: Azure Monitor Logs reference - AegDeliveryFailureLogs
description: Reference for AegDeliveryFailureLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AegDeliveryFailureLogs

 Azure Event Grid - event delivery failure logs.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Event Grid Topics
- Event Grid Domains
- Event Grid Partner Topics
- Event Grid System Topics




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Category | string | Log category name. |
| EventSubscriptionName | string | Name of the event subscription. |
| _IsBillable | string |  |
| Message | string | Log message for the user. |
| OperationName | string | Name of the operation. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| SubResourceName | string | Name of the sub resource. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time when log was generated. |
| Type | string | The name of the table |
