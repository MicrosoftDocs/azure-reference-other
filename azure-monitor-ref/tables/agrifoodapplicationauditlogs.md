---
title: Azure Monitor Logs reference - AgriFoodApplicationAuditLogs
description: Reference for AgriFoodApplicationAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# AgriFoodApplicationAuditLogs

 Logs for privileged actions such as data-plane resource create, update, delete and subscription management operations.

## Categories

- Audit
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Microsoft.AgFoodPlatform/farmBeats




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallerIpAddress | string | IP address of the client that made the request. |
| Category | string | Logs generated as a result of operations executed using FarmBeats APIs are grouped into categories. Categories in FarmBeats are logical groupings based on either the data source the underlying APIs fetch data from or on the basis of hierarchy of entities in FarmBeats. |
| CorrelationId | string | Unique identifier to be used to correlate logs, when available. |
| DataPlaneResourceId | string | ID that uniquely identifies a FarmBeats resource such as a Farm, Farmer, Boundary etc. |
| Identity | dynamic | Identity from the token that was presented in the REST API request. |
| Level | string | The severity level of the event, will be one of Informational, Warning, Error, or Critical. |
| Location | string | The region of the resource emitting the event. |
| OperationName | string | The operation name for which the log entry was created. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Additional details about the result, when available. |
| ResultType | string | Result of the REST API request. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (in UTC) when the log was created. |
| Type | string | The name of the table |
