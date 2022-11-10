---
title: Azure Monitor Logs reference - ResourceManagementPublicAccessLogs
description: Reference for ResourceManagementPublicAccessLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# ResourceManagementPublicAccessLogs

 Contains Resource management private link analysis events such as the operations that are already blocked due to private link present at the scope or operations that would be blocked. Contains information from the entire tenant.

## Categories

- Azure Resources
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallerIpAddress | string | Client IP address. |
| Category | string | A category type associated with the operation. |
| CorrelationId | string | An event ID that can be used to correlated events between multiple tables. |
| DurationMs | long | Amount of time (in milliseconds) taken by the operation. |
| ObjectIdentifier | string | Object ID for the caller of the operation. |
| OperationName | string | The operation associated with the log record. |
| OperationType | string | The resource type and operation associated with the log record. |
| OperationVersion | string | An API version associated with the operation. |
| PrivateLinkAssociationIds | dynamic | List of private link association resource IDs present at the scope. |
| ProviderName | string | The resource provider name associated with the log record. |
| ResultSignature | int | Status code of the operation. It covers success and failure. |
| ResultType | string | Status of the operation. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log entry was generated. |
| Type | string | The name of the table |
| Uri | string | The resource URI for the operation. |
