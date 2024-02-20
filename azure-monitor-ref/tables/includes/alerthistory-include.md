---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AlertHistory
---


| Column | Type | Description |
|---|---|---|
| AlertContext | string |   |
| AlertDescription | string |   |
| AlertId | string |   |
| AlertName | string |   |
| AlertPriority | string |   |
| AlertSeverity | string |   |
| AlertState | string |   |
| _BilledSize | real | The record size in bytes |
| Custom1 | string |   |
| Custom10 | string |   |
| Custom2 | string |   |
| Custom3 | string |   |
| Custom4 | string |   |
| Custom5 | string |   |
| Custom6 | string |   |
| Custom7 | string |   |
| Custom8 | string |   |
| Custom9 | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastModifiedBy | string |   |
| ManagementGroupName | string |   |
| RepeatCount | int |   |
| ResolvedBy | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceDisplayName | string |   |
| SourceFullName | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TicketId | string |   |
| TimeGenerated | datetime |   |
| TimeLastModified | datetime |   |
| TimeRaised | datetime |   |
| TimeResolved | datetime |   |
| Type | string | The name of the table |
