---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ACSNetworkTraversalDiagnostics
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| BytesReceived | long | Number of bytes received by the client. |
| BytesSent | long | Number of bytes sent by the client. |
| CallerIpAddress | string | The caller IP address, if the operation corresponds to an API call that would come from an entity with a publicly available IP address. |
| Category | string | The log category of the event. Logs with the same log category and resource type will have the same properties fields. |
| CorrelationId | string | The ID associated with the relay session. |
| Identity | string | The request sender's identity, if provided when requesting the relay configuration used to establish the session. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The severity level of the operation. |
| OperationName | string | The operation associated with log record. |
| Protocol | string | The protocol used for the session (e.g. TCP or UDP). |
| Reason | string | Describes the reason for the relay session ending (e.g. Deallocated or Expired). Only defined for logs of the operation RelaySessionEnd. |
| RelayLocation | string | The location of the relay server. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | string | The sub status of the operation. If this operation corresponds to a REST API call, this field is the HTTP status code of the corresponding REST call. |
| ResultType | string | The status of the operation (e.g. Succeeded or Failed). |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| TotalBytesFromClient | long | Number of bytes received from a client during the session. |
| TotalBytesToClient | long | Number of bytes sent to a client during the session. |
| Type | string | The name of the table |
