---
title: Azure Monitor Logs reference - PurviewSecurityLogs
description: Reference for PurviewSecurityLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# PurviewSecurityLogs

 Table containing audit events for the Purview account, such as role assignments to a collection or creation or deletion of a collection.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Microsoft.Purview/accounts




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| CallerIdentities | dynamic | Contains information about the identity that performed the operation. May contain the objectId, username, PUID etc. of the identity. |
| EntityName | string | Name of the entity for which the operation was performed. |
| EntityType | string | Type of the entity for which the operation was performed. |
| _IsBillable | string |  |
| Location | string | Location of the Purview account. |
| OperationName | string | The operation associated with log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Description of the result of the operation. May also contain the error description if the operation failed. |
| ResultType | string | Result of the operation. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) when the log was generated. |
| Type | string | The name of the table |
