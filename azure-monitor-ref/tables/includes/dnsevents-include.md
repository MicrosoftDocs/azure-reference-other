---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: DnsEvents
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClientIP | string |   |
| Computer | string |   |
| Confidence | string |   |
| Description | string |   |
| EventId | int |   |
| IndicatorThreatType | string |   |
| IPAddresses | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MaliciousIP | string |   |
| Message | string |   |
| Name | string |   |
| QueryType | string |   |
| RemoteIPCountry | string |   |
| RemoteIPLatitude | real |   |
| RemoteIPLongitude | real |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Result | string |   |
| ResultCode | int |   |
| Severity | int |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SubType | string |   |
| TaskCategory | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
