---
title: Azure Monitor Logs reference - PFTitleAuditLogs
description: Reference for PFTitleAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# PFTitleAuditLogs

 Provides audit logs for various types of action performed on Azure PlayFab Title.

## Categories

- Audit
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure PlayFab




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Level | string | The severity level of the log, will be one of Informational, Warning, Error, or Critical. |
| Location | string | The region of the Azure PlayFab Title, generating the log. |
| ModifiedPlayerId | string | Player ID on which the action taken. |
| OperationName | string | The operation name combined with operation type represents the action performed for which the log was generated. |
| OperationType | string | The operation name combined with operation type represents the action performed for which the log was generated. |
| PlayFabPlayerAccountPoolId | string | ID of Azure PlayFab PlayerAccountPool associated with the Azure PlayFab Title for which the log was generated. |
| PlayFabTitleId | string | ID of Azure PlayFab Title for which the log was generated. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the log was generated. |
| Type | string | The name of the table |
| UserId | string | ID of the user who performed the action which generated the log. |
| UserName | string | Name or Email of the user who performed the action which generated the log. |
