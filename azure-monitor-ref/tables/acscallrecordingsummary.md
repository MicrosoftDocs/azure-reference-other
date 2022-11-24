---
title: Azure Monitor Logs reference - ACSCallRecordingSummary
description: Reference for ACSCallRecordingSummary table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# ACSCallRecordingSummary

 Call recording summary logs provide an overview about a recording maed through ACS. There is one log for every recording done, and logs contain information about the duration of the recording, the content (e.g. Audio-Video, Unmixed, Transcription, etc.) and format (e.g. WAV, MP4, etc) types used for the recording, as well as the end reason of recording.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Communication Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AudioChannelsCount | int | Total number of audio channels in the recording. |
| ChannelType | string | The recording's channel type, i.e. mixed, unmixed. |
| ChunkCount | int | The total number of chunks created fot the recording. |
| ContentType | string | The recording's content, i.e. Audio Only, Audio - Video, Transcription, etc. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| FormatType | string | The recording's file format. |
| Level | string | The severity level of the operation. |
| OperationName | string | The operation associated with log record. |
| RecordingEndReason | string | The reason why the recording ended. |
| RecordingId | string | The ID given to the recording this log refers to. |
| RecordingLength | real | Duration of the recording in seconds. |
| RecordingStartTime | datetime | The time that the recording started. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The status of the operation. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
