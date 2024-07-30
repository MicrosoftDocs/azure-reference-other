---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: WVDFeeds
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClientOS | string | The OS of the client that is requesting the feed (if available). |
| ClientSideIPAddress | string | The remote IP address from the client side. |
| ClientType | string | The type of the client that is requesting the feed (if available). |
| ClientVersion | string | The version of the client that is requesting the feed (if available). |
| CorrelationId | string | The activity Id. |
| IconFail | int | The number of Icons (PNG, ICO) files that failed to be retrieved. |
| IconTotal | int | The total number of Icons (PNG, ICO) files that the client attempted to retrieve. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsClientPrivateLink | string | True if the client used a private link endpoint for the feed request. |
| RDPFail | int | The number of RDP files that failed to be retrieved. |
| RDPTotal | int | The total number of RDP files that the client attempted to retrieve. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
| UserName | string | The user that initiated the feed request. |
