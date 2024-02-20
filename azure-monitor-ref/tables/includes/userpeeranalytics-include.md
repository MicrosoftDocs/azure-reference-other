---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: UserPeerAnalytics
---


| Column | Type | Description |
|---|---|---|
| AADTenantId | string | Unique identifier of the Azure Tenant |
| _BilledSize | real | The record size in bytes |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| PeerUserId | string | Unique identifier of the peer of the primary user |
| PeerUserName | string | User name of the peer of the primary user |
| PeerUserPrincipalName | string | User principal name of the peer of the primary user |
| Rank | int | Rank of the peer with respect to the primary user |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp when the peer analytics is calculated |
| Type | string | The name of the table |
| UserId | string | Unique identifier of the primary user |
| UserName | string | User name of the primary user |
| UserPrincipalName | string | User principal name of the primary user |
