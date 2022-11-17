---
title: Azure Monitor Logs reference - AgriFoodJobProcessedLogs
description: Reference for AgriFoodJobProcessedLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# AgriFoodJobProcessedLogs

 Logs indicating success or failure of job runs for farmOperationDataIngestionJob, farmOperationPeriodicJob, farmOperationEventHandlingJob,satelliteDataIngestionJob, weatherDataIngestionJob etc. These logs also contain reasons for failure of these jobs if any.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Microsoft.AgFoodPlatform/farmBeats




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationId | string | ApplicationId in identity claims. |
| Category | string | Logs generated as a result of operations executed using FarmBeats APIs are grouped into categories. Categories in FarmBeats are logical groupings based on either the data source the underlying APIs fetch data from or on the basis of hierarchy of entities in FarmBeats. |
| ClientTenantId | string | TenantId in identity claims. |
| CorrelationId | string | Unique identifier to be used to correlate logs, when available. |
| DurationMs | real | Time it took to service the REST API request, in milliseconds. |
| FarmerId | string | Farmer ID associated with the request, wherever applicable. |
| InitiatedBy | string | Indicates whether the job was initiated by FarmBeats or user. |
| JobId | string | User defined ID of the job. |
| JobRunType | string | Indicates whether a job is a periodic job or a one-time job. |
| Level | string | The severity level of the event, will be one of Informational, Warning, Error, or Critical. |
| Location | string | The region of the resource emitting the event. |
| ObjectId | string | ObjectId in identity claims. |
| OperationName | string | The operation name for which the log entry was created. |
| Properties | dynamic | Additional properties associated with the Job. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Additional details about the result, when available. |
| ResultType | string | Result of the REST API request. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (in UTC) when the log was created. |
| Type | string | The name of the table |
