---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AADB2CRequestLogs
---


| Column | Type | Description |
|---|---|---|
| AADTenantId | string | The AAD tenant ID of associated request. |
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string | Hashed format of caller IP address. Can be used to identify if a single IP address is using a large portion of traffic. |
| CorrelationId | string | The ID for correlated log analytics events. Can be used to identify correlated events between multiple tables. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | Name of the operation. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | string | The HTTP status code of the corresponding REST call. |
| ResultType | string | Indicates whether the request is throttled or not. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The date and time of the request received at the AAD gateway in UTC. |
| Type | string | The name of the table |
