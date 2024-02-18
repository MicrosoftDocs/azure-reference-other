---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AmlRegistryWriteEventsLog
---


| Column | Type | Description |
|---|---|---|
| AssetName | string | AzureML Asset name associated with log record. |
| AssetVersion | string | AzureML Asset version associated with log record. |
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | The correlation ID associated with log record. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Labels | string | Labels associated with log record. |
| RegistryResourceId | string | ARM ResourceId of the registry that generated this log record. |
| RegistryTenantId | string | TenantId associated with log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserName | string | User name who initialized the event. |
| UserObjectId | string | User AAD object ID who initialized the event. |
