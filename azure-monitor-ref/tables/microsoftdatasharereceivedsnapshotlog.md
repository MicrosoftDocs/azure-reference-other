---
title: Azure Monitor Logs reference - MicrosoftDataShareReceivedSnapshotLog
description: Reference for MicrosoftDataShareReceivedSnapshotLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 3/19/2021
---

# MicrosoftDataShareReceivedSnapshotLog

 Microsoft Data Share Synchronization Log

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Data Share




## Columns

|Column|Type|Description|
|---|---|---|
|Category|string|The name of the log that belongs to|
|CorrelationId|string|correlationId|
|DataSetMappingType|string|Blob/container/bolbfolder…etc|
|DataSetName|string|Dataset name|
|DataSetType|string|Blob/container/bolbfolder…etc|
|DetailMessage|string|gives the event detail. Can be empty if synchronization is not finished.|
|EndTime|string|End time, can be empty if job not finished|
|FilesRead|string|Number of files read from source|
|FilesWritten|string|Number of files written into sink |
|OperationName|string|The name of the operation represented by this event|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SizeRead|string|Size of files read from source|
|SizeWritten|string|Size of files into sink in bytes|
|SourceSystem|string||
|StartTime|string|Start Time|
|Status|string|Synchronization status, inprogress/succeed/failed|
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of the log|
|TriggerType|string|Ondemand/trigger|
|Type|string|The name of the table|
