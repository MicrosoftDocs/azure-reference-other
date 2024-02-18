---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AzureAttestationDiagnostics
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string | IP Address of the client that submitted the request. |
| ContentLength | int | Length of the content body in bytes. |
| ContentType | string | Content-Type header value passed by the client. |
| DurationMs | real | Amount of time it took to process request in milliseconds. |
| FailureDetails | string | Details of the request failure, if it failed. Blank if the request succeeded. |
| Identity | dynamic | JSON structure containing information about the caller. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | Error or Informational message indicating if the service processed the request. |
| OperationName | string | Name of the operation attempted on the resource. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceRegion | string | Region where the resource is located. |
| ResourceUri | string | URI of the resource. |
| ResultDetails | string | Detailed response messages included in the result, if available. |
| ResultSignature | string | HTTP status code returned from the service. |
| ResultType | string | Indicates if the request was successful or failed. |
| ServiceLocation | string | Location of the service which processed the request. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Date and time the record was created. |
| TraceContext | dynamic | W3C trace context. |
| Type | string | The name of the table |
| UserAgent | string | HTTP header passed by the client, if applicable. |
