---
title: Azure Monitor Logs reference - AHDSDicomAuditLogs
description: Reference for AHDSDicomAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/1/2023
---

# AHDSDicomAuditLogs

 Data plane audit logs of privileged actions made against Azure Health Data DICOM service. For example, storing a DICOM instance.

## Categories

- Audit
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Health Data Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| CorrelationId | string | An identifier used to group together a set of related events. |
| Identity | dynamic | Identity of the issuer of the request. |
| _IsBillable | string |  |
| Level | string | The log's severity level. Possible values are Informational, Warning, and Error. |
| OperationName | string | The operation name for which the log entry was generated. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | Indicates whether the operation started or ended. |
| SourceSystem | string |  |
| StatusCode | int | Status code returned for the request. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time (UTC) when the log was created. |
| Type | string | The name of the table |
| Uri | string | URI of the request. |
