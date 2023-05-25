---
title: Azure Monitor Logs reference - ACSCallAutomationMediaSummary
description: Reference for ACSCallAutomationMediaSummary table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 5/26/2023
---

# ACSCallAutomationMediaSummary

 Communication Services summary logs of Call Automation Media operations. Every entry corresponds to the result of a call to the Call Automation Media APIs. (e.g. Play, Recognize).

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Communication Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| _IsBillable | string |  |
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
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
