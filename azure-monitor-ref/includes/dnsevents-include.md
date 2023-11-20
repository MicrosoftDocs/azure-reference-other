---
ms.service: azure-monitor
ms.topic: include
ms.date: 08/28/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: DnsEvents
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClientIP | string | IP address of the DNS Client - the machine that made the query |
| Computer | string | The computer name of the DNS Server to where a DNS query is sent |
| Confidence | string |   |
| Description | string |   |
| EventId | int |   |
| IndicatorThreatType | string |   |
| IPAddresses | string | List of IP addresses (comma-separated) that resolve to the queried domain |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MaliciousIP | string |   |
| Message | string |   |
| Name | string | The DNS domain queried  |
| QueryType | string | DNS record Type. Ex: A, AAAA, CNAME, MX, NS, PTR, SOA, etc.  |
| RemoteIPCountry | string |   |
| RemoteIPLatitude | real |   |
| RemoteIPLongitude | real |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Result | string |   |
| ResultCode | int |   |
| Severity | int |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SubType | string | DNS query sub type. Ex: LookupQuery, DynamicRegistration and ConfigurationChange  |
| TaskCategory | string |   |
| TimeGenerated | datetime | The timestamp of the event  |
| Type | string | The name of the table |
