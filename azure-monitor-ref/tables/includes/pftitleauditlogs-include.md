---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: PFTitleAuditLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The severity level of the log, will be one of Informational, Warning, Error, or Critical. |
| Location | string | The region of the Azure PlayFab Title, generating the log. |
| ModifiedPlayerId | string | Player ID on which the action taken. |
| OperationName | string | The operation name combined with operation type represents the action performed for which the log was generated. |
| OperationType | string | The operation name combined with operation type represents the action performed for which the log was generated. |
| PlayFabPlayerAccountPoolId | string | ID of Azure PlayFab PlayerAccountPool associated with the Azure PlayFab Title for which the log was generated. |
| PlayFabTitleId | string | ID of Azure PlayFab Title for which the log was generated. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the log was generated. |
| Type | string | The name of the table |
| UserId | string | ID of the user who performed the action which generated the log. |
| UserName | string | Name or Email of the user who performed the action which generated the log. |
