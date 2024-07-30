---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: BlockchainProxyLog
---


| Column | Type | Description |
|---|---|---|
| Agent | string |   |
| _BilledSize | real | The record size in bytes |
| BlockchainMemberName | string |   |
| BlockchainNodeName | string |   |
| Category | string |   |
| Code | string |   |
| Consortium | string |   |
| EthMethod | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LogLevel | string |   |
| NodeHost | string |   |
| NodeLocation | string |   |
| OperationName | string |   |
| PublicUser | string |   |
| Remote | string |   |
| RequestMethodName | string |   |
| RequestSize | int |   |
| RequestTime | real |   |
| Resource | string |   |
| ResourceGroup | string |   |
| ResourceId | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceProvider | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SubscriptionId | string |   |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tenant | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
