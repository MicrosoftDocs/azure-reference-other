---
title: Azure Monitor Logs reference - MicrosoftDataShareReceivedSnapshotLog
description: Reference for MicrosoftDataShareReceivedSnapshotLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# MicrosoftDataShareReceivedSnapshotLog

 Data Share consumer side synchronization logs.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Data Share




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | The name of the log that belongs to |
| CorrelationId | string | CorrelationId of the event, this can be use as a reference to join with other tables |
| DataSetMappingType | string | Indicating the dataSetMapping type, this can be Blob/container/bolbfolder,etc |
| DataSetName | string | Name of provider source dataset |
| DataSetType | string | Indicating the dataSet type, this can be Blob/container/bolbfolder,etc |
| DetailMessage | string | This shows the event details. Can be empty if synchronization is not finished |
| EndTime | string | Datashare synchronization end time, can be empty if job not finished |
| FilesRead | string | Number of files read from source |
| FilesWritten | string | Number of files written into sink |
| OperationName | string | The name of the operation represented by this event |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SizeRead | string | Size of files read from source |
| SizeWritten | string | Size of files into sink in bytes |
| SourceSystem | string |  |
| StartTime | string | Datashare synchronization start time |
| Status | string | Synchronization status, can be inprogress/succeed/failed |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The time (UTC) when the event is generated |
| TriggerType | string | Indicating whether the trigger is on-demand trigger or manual trigger |
| Type | string | The name of the table |
