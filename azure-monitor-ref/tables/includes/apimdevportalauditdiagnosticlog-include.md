---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/22/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: APIMDevPortalAuditDiagnosticLog
---


| Column | Type | Description |
|---|---|---|
| ActivityId | string | An unique identifier represented as a GUID (Globally Unique Identifier). It serves as a globally distinctive label for tracking and correlating activities or events across systems and applications. |
| ApimClient | string | The field refers to the HTTP header X-Ms-Apim-Client sent by Developer Portal. |
| _BilledSize | real | The record size in bytes |
| Category | string | Distinct group or type of record. |
| HashedUserId | string | The field represents a hashed or encrypted form of a user identifier. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | Field denotes the specific name or identifier of the operation being performed. |
| Region | string | The field indicates the geographical location or data center region within the Azure cloud infrastructure where a specific resource or service is deployed. |
| RequestMethod | string | The field indicates the type of HTTP method used in an incoming request. |
| RequestPath | string | The field contains the path or endpoint of an incoming request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseCode | int | The field indicates the HTTP status code associated with the server's response to a client's request. |
| ResultType | string | This field signifies the outcome or type of result associated with this operation. It has two values: Succeeded or Failed |
| ServiceName | string | API Management service name |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Represents the date and time when the associated event or record was generated. |
| Type | string | The name of the table |
| UserAgent | string | The field refers to the HTTP header that provides information about the user's browser or client application. |
| Version | string | API Management version |
