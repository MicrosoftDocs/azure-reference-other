---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/15/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ACSCallClosedCaptionsSummary
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CancelReason | string | The reason why the closed captions cancelled. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| Duration | real | Duration of the closed captions in seconds. |
| EndReason | string | The reason why the closed captions ended. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The severity level of the operation. |
| OperationName | string | The operation associated with log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The status of the operation. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SpeechRecognitionSessionId | string | The ID given to the closed captions this log refers to. |
| SpokenLanguage | string | The spoken language of the closed captions. |
| StartTime | datetime | The time that the closed captions started. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
