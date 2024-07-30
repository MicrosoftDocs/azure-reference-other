---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ACSCallAutomationMediaSummary
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The severity level of the operation. |
| OperationId | string | The ID for media events. Can be used to identify operation events between ACSCallAutomationIncomingOperations table and this. |
| OperationName | string | The operation associated with log record. |
| PlayInLoop | bool | Describes if the Play was requested to loop. |
| PlayInterrupted | bool | Describes if the play operation was interrupted. |
| PlayToParticipant | bool | True if Play request was targeted to a single participant, false if it was played to all participants. |
| RecognizePromptSubOperationName | string | Describes the Recognize request's prompt kind, i.e. SSML, Text, File. Only available when Prompt is requested during Recognize operation. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultCode | int | The HTTP result code for the operation. |
| ResultMessage | string | The result message related to the operation. |
| ResultSubcode | int | The sub status code for the operation. |
| ResultType | string | The status of the operation. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
