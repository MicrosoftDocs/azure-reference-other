---
ms.service: azure-monitor
ms.topic: include
ms.date: 12/04/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AzureBackupOperations
---


| Column | Type | Description |
|---|---|---|
| BackupManagementType | string | Type of workload associated with the operation, for example, DPM, Azure Backup Server, Azure Backup Agent (MAB). |
| _BilledSize | real | The record size in bytes |
| Category | string | Category of the log, for example, AzureBackupOperations. |
| ExtendedProperties | dynamic | Additional properties applicable to the operation, for example, the associated backup item or server. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | High-level name of the action that is logged to this table, for example, DataOperations. |
| OperationStartTime | datetime | The start time of the operation. |
| OperationType | string | Type of the Azure Backup operation executed, for example, stop backup with delete data, modify policy, change passphrase. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SchemaVersion | string | The schema version. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) when the log was generated. |
| Type | string | The name of the table |
