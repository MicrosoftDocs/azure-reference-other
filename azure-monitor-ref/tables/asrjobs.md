---
title: Azure Monitor Logs reference - ASRJobs
description: Reference for ASRJobs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/31/2023
---

# ASRJobs

 This table contains records of Azure Site Recovery (ASR) jobs such as failover, test failover, reprotection etc., with key details for monitoring and diagnostics, such as the replicated item information, duration, status, description and so on. Whenever an ASR job is completed (i.e., succeeded or failed), a corresponding record for the job is sent to this table. You can view history of ASR jobs by querying this table over a larger time range, provided your workspace has the required retention configured.

## Categories

- Audit
## Solutions

- LogManagement
## Resource types

- Recovery Services Vaults




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real | The record size in bytes |
| Category | string | The category of the log. |
| CorrelationId | string | Correlation ID associated with the ASR job for debugging purposes. |
| DurationMs | int | Duration of the ASR job. |
| EndTime | datetime | End time of the ASR job. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| JobUniqueId | string | Unique ID of the ASR job. |
| OperationName | string | Type of ASR job, for example, Test failover. |
| PolicyFriendlyName | string | Friendly name of the replication policy applied to the replicated item (if applicable). |
| PolicyId | string | ARM ID of the replication policy applied to the replicated item (if applicable). |
| PolicyUniqueId | string | Unique ID of the replication policy applied to the replicated item (if applicable). |
| ReplicatedItemFriendlyName | string | Friendly name of replicated item associated with the ASR job (if applicable). |
| ReplicatedItemId | string | ARM ID of the replicated item associated with the ASR job (if applicable). |
| ReplicatedItemUniqueId | string | Unique ID of the replicated item associated with the ASR job (if applicable). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Result of the ASR job. |
| SourceFriendlyName | string | Friendly name of the resource on which the ASR job was executed. |
| SourceResourceId | string | ARM Id of the resource on which the ASR job was executed. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
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
