---
title: Azure Monitor Logs reference - MicrosoftDataShareSentSnapshotLog
description: Reference for MicrosoftDataShareSentSnapshotLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# MicrosoftDataShareSentSnapshotLog

 Microsoft Data Share Synchronization Log

## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime|The timestamp (UTC) of the log|
|OperationName|string|The name of the operation represented by this event|
|Category|string|The name of the log that belongs to|
|CorrelationId|string|correlationId|
|DetailMessage|string|gives the event detail. Can be empty if synchronization is not finished.|
|StartTime|string|Start Time|
|EndTime|string|End time, can be empty if job not finished|
|Status|string|Synchronization status, inprogress/succeed/failed|
|TriggerType|string|Ondemand/trigger|
|DataSetMappingType|string|Blob/container/bolbfolder…etc|
|DataSetType|string|Blob/container/bolbfolder…etc|
|DataSetName|string|Dataset name|
|FilesWritten|string|Number of files written into sink |
|FilesRead|string|Number of files read from source|
|SizeWritten|string|Size of files into sink in bytes|
|SizeRead|string|Size of files read from source|
|Type|string||
|_ResourceId|string||
