---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ACSCallSurvey
---


| Column | Type | Description |
|---|---|---|
| AudioIssues | string | Comma separated audio issues reported by the participant. |
| AudioRatingScore | int | Audio experience rated by the participant. |
| AudioRatingScoreLowerBound | int | Minimum value of the AudioRatingScore scale. |
| AudioRatingScoreThreshold | int | The AudioRatingScore greater than this value indicates better quality. |
| AudioRatingScoreUpperBound | int | Maximum value of the AudioRatingScore scale. |
| _BilledSize | real | The record size in bytes |
| CallId | string | The identifier of the call used to correlate. Can be used to identify correlated events between multiple tables. |
| CorrelationId | string | The ID for correlated events. This field contains the participant ID that allows call survey to be correlated with other calling logs. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API-version associated with the operation or version of the operation (if there is no API version). |
| OverallCallIssues | string | Comma separated overall issues reported by the participant. |
| OverallRatingScore | int | Overall call experience rated by the participant. |
| OverallRatingScoreLowerBound | int | Minimum value of the OverallRatingScore scale. |
| OverallRatingScoreThreshold | int | The OverallRatingScore greater than this value indicates better quality. |
| OverallRatingScoreUpperBound | int | Maximum value of the OverallRatingScore scale. |
| ParticipantId | string | ID of the participant. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ScreenshareIssues | string | Comma separated screenshare issues reported by the participant. |
| ScreenshareRatingScore | int | Screenshare experience rated by the participant. |
| ScreenshareRatingScoreLowerBound | int | Minimum value of the ScreenshareRatingScore scale. |
| ScreenshareRatingScoreThreshold | int | The ScreenshareRatingScore greater than this value indicates better quality. |
| ScreenshareRatingScoreUpperBound | int | Maximum value of the ScreenshareRatingScore scale. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SurveyId | string | The ID of the survey uniquely identifies the call survey. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| VideoIssues | string | Comma separated video issues reported by the participant. |
| VideoRatingScore | int | Video experience rated by the participant. |
| VideoRatingScoreLowerBound | int | Minimum value of the VideoRatingScore scale. |
| VideoRatingScoreThreshold | int | The VideoRatingScore greater than this value indicates better quality. |
| VideoRatingScoreUpperBound | int | Maximum value of the VideoRatingScore scale. |
