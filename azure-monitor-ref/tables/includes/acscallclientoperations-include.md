---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ACSCallClientOperations
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CallClientTimeStamp | datetime | The timestamp (UTC) of when the call client log was generated. |
| CallId | string | The identifier of the call used to correlate. Can be used to identify correlated events between multiple tables. |
| ClientInstanceId | string | Client instance ID. |
| DurationMs | long | Client operation duration in millisecond. |
| EndpointId | string | Azure Communication Service calling endpoint ID. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationId | string | Client operation ID. |
| OperationName | string | The operation associated with log record. |
| OperationPayload | dynamic | Azure Communication Service calling specific operation payload adhering to a defined schema. |
| OperationType | string | Client operation type. |
| ParticipantId | string | ID of the participant. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | int | Client operation event result network code. |
| ResultType | string | Client operation event result type. |
| SdkVersion | string | Azure Communication Service calling client SDK version associated with the log. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserAgent | string | The user agent string of the client application. |
