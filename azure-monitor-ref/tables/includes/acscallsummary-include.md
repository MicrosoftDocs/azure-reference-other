---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ACSCallSummary
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CallDuration | long | Duration of the call in seconds. |
| CallStartTime | datetime | Start time of the call. |
| CallType | string | Type of the call, for example P2P (peer to peer). |
| Category | string | The log category of the event. Logs with the same log category and resource type will have the same properties fields. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| EndpointId | string | The ID of the endpoint. |
| EndpointType | string | Type of the endpoint, for example VoIP (voice over IP). |
| Identifier | string | The indentifier of the call used to correlate. Can be used to identify correlated events between multiple tables. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API-version associated with the operation or version of the operation (if there is no API version). |
| OsVersion | string | Operating System version. |
| ParticipantDuration | long | Duration of the participant call in seconds. |
| ParticipantEndReason | string | Participant's call end reason. |
| ParticipantId | string | ID of the participant. |
| ParticipantStartTime | datetime | Start time of the participant. |
| ParticipantTenantId | string | The ID of the Microsoft tenant associated with the participant. |
| ParticipantType | string | Description of the participant as a combination of its client (ACS or Teams) and its identity (ACS or Microsoft 365). Possible values include ACS, Teams, ACS as Teams external user, and ACS as Microsoft 365 user. |
| PstnParticipantCallType | string | The type and direction of PSTN participants, including emergency calling, direct routing, transfer, forwarding, etc. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SdkVersion | string | SDK version. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TeamsThreadId | string | Thread ID of the team. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
