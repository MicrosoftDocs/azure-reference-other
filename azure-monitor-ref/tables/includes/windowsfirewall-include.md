---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: WindowsFirewall
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CommunicationDirection | string |   |
| Computer | string |   |
| Confidence | string |   |
| Description | string |   |
| DestinationIP | string |   |
| DestinationPort | int |   |
| FirewallAction | string |   |
| FirstReportedDateTime | string |   |
| FullDestinationAddress | string |   |
| IndicatorThreatType | string |   |
| Info | string |   |
| IsActive | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastReportedDateTime | string |   |
| MaliciousIP | string |   |
| MaliciousIPCountry | string |   |
| MaliciousIPLatitude | real |   |
| MaliciousIPLongitude | real |   |
| ManagementGroupName | string |   |
| Protocol | string |   |
| RemoteIP | string |   |
| RequestSizeInBytes | long |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Severity | int |   |
| SourceIP | string |   |
| SourcePort | int |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |   |
| TLPLevel | string |   |
| Type | string | The name of the table |
