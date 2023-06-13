---
title: Azure Monitor Logs reference - ACSCallRecordingIncomingOperations
description: Reference for ACSCallRecordingIncomingOperations table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# ACSCallRecordingIncomingOperations

 Communication Services logs of incoming requests to Call Recording operations. Every entry corresponds to the result of a call to the Call Recording APIs, e.g. StartRecording, StopRecording, PauseRecording, ResumeRecording, etc.

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
| CallConnectionId | string | Id of the call connection/leg, if available. |
| CallerIpAddress | string | The caller IP address, if the operation corresponds to an API call that would come from an entity with a publicly available IP address. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| DurationMs | int | The duration of the operation in milliseconds. |
| _IsBillable | string |  |
| Level | string | The severity level of the operation. |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API version associated with the operation or version of the operation (if there is no API version). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | int | The sub status of the operation. If this operation corresponds to a REST API call, this field is the HTTP status code of the corresponding REST call. |
| ResultType | string | The status of the operation. |
| SdkType | string | The SDK type used in the request. |
| SdkVersion | string | SDK Version. |
| ServerCallId | string | Server Call Id. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| URI | string | The URI of the request. |
