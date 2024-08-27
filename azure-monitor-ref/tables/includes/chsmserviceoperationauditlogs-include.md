---
ms.service: azure-monitor
ms.topic: include
ms.date: 08/26/2024
ms.author: orens
author: osalzberg
ms.custom: CHSMServiceOperationAuditLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string | IP address of the client that made the request. |
| ClientInfo | string | User agent information. |
| ClientSdkPackageVersion | string | Version of the client SDK package. |
| DurationMs | int | Time it took to service the request, in milliseconds. This does not include the network latency, so the time you measure on the client side might not match this time. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MemberId | string | Member ID of HSM in the Cloud HSM cluster. |
| Opcode | string | Operation code in HEX string format. |
| OperationName | string | Name of the operation |
| PoolType | string | Cloud HSM pool type. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | More detailed description of the result. |
| ResultSignature | string | Short signature of the result. |
| ResultType | string | Result of the request. |
| Sku | dynamic | Information about the Cloud HSM SKU including family and name. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when operation occured. |
| Type | string | The name of the table |
