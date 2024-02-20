---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AMSStreamingEndpointRequests
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClientIP | string | IP address of the client. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | Message level. Possible values are Informational, Warning, Error, Critical and Verbose. |
| Location | string | Location of the service sending the event. |
| OperationName | string | The name of the operation that triggered the event. |
| OperationVersion | string | Azure Media Services operation version. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string | Status code of the request. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) when the event was generated. |
| Type | string | The name of the table |
| URL | string | The streaming URL from Azure Media Services. |
