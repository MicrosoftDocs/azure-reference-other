---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ACSNetworkTraversalIncomingOperations
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The log category of the event. Logs with the same log category and resource type will have the same properties fields. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| DurationMs | int | The duration of the operation in milliseconds. |
| Identity | string | The request sender's identity, if provided. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The severity level of the operation. |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API-version associated with the operation or version of the operation (if there is no API version). |
| PlatformType | string | The platform type being used in the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | string | The sub status of the operation. If this operation corresponds to a REST API call, this field is the HTTP status code of the corresponding REST call. |
| ResultType | string | The status of the operation (e.g. Succeeded or Failed). |
| RouteType | string | The routing methodology to where the ICE server will be located from the client (e.g. Any or Nearest). |
| SdkType | string | The SDK type being used in the request. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| TTL | string | The TTL specified in the request. |
| Type | string | The name of the table |
| URI | string | The URI of the request |
