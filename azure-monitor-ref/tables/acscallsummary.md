---
title: Azure Monitor Logs reference - ACSCallSummary
description: Reference for ACSCallSummary table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# ACSCallSummary

 Call summary logs provide an overview about a call made through ACS. There is one log for every participant in the call, and logs contain information about the duration of the call, the duration of the individual participant, the type of participant (e.g. VoIP, PSTN, etc.), as well as the endpoint information like the OS version being used, or the SDK version of the ACS platform.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Communication Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallDuration | long | Duration of the call in seconds. |
| CallStartTime | datetime | Start time of the call. |
| CallType | string | Type of the call, for example P2P (peer to peer). |
| Category | string | The log category of the event. Logs with the same log category and resource type will have the same properties fields. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| EndpointId | string | ID of the endpoint. |
| EndpointType | string | Type of the endpoint, for example VoIP (voice over IP). |
| Identifier | string | The indentifier of the call used to correlate. Can be used to identify correlated events between multiple tables. |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API-version associated with the operation or version of the operation (if there is no API version). |
| OsVersion | string | Operating System version. |
| ParticipantDuration | long | Duration of the participant call in seconds. |
| ParticipantEndReason | string | Participant's call end reason. |
| ParticipantId | string | ID of the participant. |
| ParticipantStartTime | datetime | Start time of the participant. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SdkVersion | string | SDK version. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TeamsThreadId | string | Thread ID of the team. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
