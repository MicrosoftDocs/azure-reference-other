---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ASRJobs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The category of the log. |
| CorrelationId | string | Correlation ID associated with the ASR job for debugging purposes. |
| DurationMs | int | Duration of the ASR job. |
| EndTime | datetime | End time of the ASR job. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| JobUniqueId | string | Unique ID of the ASR job. |
| OperationName | string | Type of ASR job, for example, Test failover. |
| PolicyFriendlyName | string | Friendly name of the replication policy applied to the replicated item (if applicable). |
| PolicyId | string | ARM ID of the replication policy applied to the replicated item (if applicable). |
| PolicyUniqueId | string | Unique ID of the replication policy applied to the replicated item (if applicable). |
| ReplicatedItemFriendlyName | string | Friendly name of replicated item associated with the ASR job (if applicable). |
| ReplicatedItemId | string | ARM ID of the replicated item associated with the ASR job (if applicable). |
| ReplicatedItemUniqueId | string | Unique ID of the replicated item associated with the ASR job (if applicable). |
| ReplicationScenario | string | Field used to identify whether the replication is being done for an Azure resource or an on-premises resource. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Result of the ASR job. |
| SourceFriendlyName | string | Friendly name of the resource on which the ASR job was executed. |
| SourceResourceGroup | string | Resource Group of the source. |
| SourceResourceId | string | ARM ID of the resource on which the ASR job was executed. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SourceType | string | Type of resource on which the ASR job was executed. |
| StartTime | datetime | Start time of the ASR job. |
| Status | string | Status of the ASR job. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) when the log was generated. |
| Type | string | The name of the table |
| VaultLocation | string | Location of the vault associated with the ASR job. |
| VaultName | string | Name of the vault associated with the ASR job. |
| VaultType | string | Type of the vault associated with the ASR job. |
| Version | string | The API version. |
