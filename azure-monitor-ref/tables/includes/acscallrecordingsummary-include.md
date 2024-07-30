---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ACSCallRecordingSummary
---


| Column | Type | Description |
|---|---|---|
| AudioChannelsCount | int | Total number of audio channels in the recording. |
| _BilledSize | real | The record size in bytes |
| ChannelType | string | The recording's channel type, i.e. mixed, unmixed. |
| ChunkCount | int | The total number of chunks created fot the recording. |
| ContentType | string | The recording's content, i.e. Audio Only, Audio - Video, Transcription, etc. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| FormatType | string | The recording's file format. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The severity level of the operation. |
| OperationName | string | The operation associated with log record. |
| RecordingEndReason | string | The reason why the recording ended. |
| RecordingId | string | The ID given to the recording this log refers to. |
| RecordingLength | real | Duration of the recording in seconds. |
| RecordingStartTime | datetime | The time that the recording started. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The status of the operation. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
