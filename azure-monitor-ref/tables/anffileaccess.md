---
title: Azure Monitor Logs reference - ANFFileAccess
description: Reference for ANFFileAccess table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# ANFFileAccess

 This table maps to audit logs generated in an ANF Volume. Here audit log caters to any file system operations done by users.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure NetApp Files




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallerIpAddress | string | IP address of client which performed this file operation. |
| Category | string | The log category this log belongs to as configured in diagnostic settings. |
| IsUserLocal | bool | Identifies if the User who has performed the File operation is local user or remote user. |
| Level | string | Log level of the log. This is always set to Informational. |
| Location | string | Location of the NetApp volume. |
| ObjectName | string | Name of the object for which this log was generated |
| ObjectType | string | Type of the object on which operation was performed. |
| OperationName | string | The name of the file operation which this log is generated for. |
| OperationTime | datetime | Time when the operation was performed. |
| OperationVersion | string | Version of the file operation. |
| Properties | dynamic | A set of file operation specific fields. Varies by OperationName. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | Indicating if the operation succeeded or failed. Values can be Audit Success, or Audit Failure |
| SchemaVersion | string | Version of the log schema. |
| SourceSystem | string |  |
| SubjectUnix | string | User Identifier who has performed the File operation. Format is uid:gid , separated by a colon. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time when the log was generated. |
| Type | string | The name of the table |
