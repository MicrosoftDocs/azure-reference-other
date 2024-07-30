---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: PurviewSecurityLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CallerIdentities | dynamic | Contains information about the identity that performed the operation. May contain the objectId, username, PUID etc. of the identity. |
| EntityName | string | Name of the entity for which the operation was performed. |
| EntityType | string | Type of the entity for which the operation was performed. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | Location of the Purview account. |
| OperationName | string | The operation associated with log record. |
| Properties | dynamic | Additional properties of the operation. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Description of the result of the operation. May also contain the error description if the operation failed. |
| ResultType | string | Result of the operation. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) when the log was generated. |
| Type | string | The name of the table |
