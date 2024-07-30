---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AppServiceHTTPLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CIp | string | IP address of the client |
| ComputerName | string | The name of the server on which the log file entry was generated. |
| Cookie | string | Cookie on HTTP request |
| CsBytes | int | Number of bytes received by server |
| CsHost | string | Host name header on HTTP request |
| CsMethod | string | The request HTTP verb |
| CsUriQuery | string | URI query on HTTP request |
| CsUriStem | string | The target of the request |
| CsUsername | string | The name of the authenticated user on HTTP request |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Referer | string | The site that the user last visited. This site provided a link to the current site |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Result | string | Success / Failure of HTTP request |
| ScBytes | int | Number of bytes sent by server |
| ScStatus | int | HTTP status code |
| ScSubStatus | string | Substatus error code on HTTP request |
| ScWin32Status | string | Windows status code on HTTP request |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SPort | string | Server port number |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time when event is generated |
| TimeTaken | int | Time taken by HTTP request in milliseconds |
| Type | string | The name of the table |
| UserAgent | string | User agent on HTTP request |
