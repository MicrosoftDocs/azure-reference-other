---
title: Azure Monitor Logs reference - DevCenterDiagnosticLogs
description: Reference for DevCenterDiagnosticLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/23/2023
---

# DevCenterDiagnosticLogs

 Data plane audit logs related to your dev center resources. Will display information concerning stop/start/deletes on dev boxes and environments.

## Categories

- Audit
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Dev Centers




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallerIdentity | string | User ID that created the request. |
| CorrelationId | string | ID which groups operation logs for ease of debugging. |
| OperationName | string | The operation stage of the service from which the log entry was generated. |
| OperationResult | string | Displays whether operation was successful or unsuccessful. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseCode | string | HTTP status code of the completed operation. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetResourceId | string | Dataplane ID of the affected resource. |
| TenantId | string |  |
| TimeGenerated | datetime | Time (UTC) when the log was created. |
| Type | string | The name of the table |
