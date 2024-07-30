---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AppPlatformIngressLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| BodyBytesSent | string | Number of bytes sent to a client, not counting the response header |
| Host | string | The host name of the log |
| HttpReferer | string | Value of the referer header |
| HttpUserAgent | string | Value of user-agent header |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The name of the operation represented by this event |
| ProxyAlternativeUpstreamName | string | Name of the alternative upstream server. The format is upstream-\<namespace\>-\<service name\>-\<service port\> |
| ProxyUpstreamName | string | Name of the upstream server. The format is upstream-\<namespace\>-\<service name\>-\<service port\> |
| RemoteAddr | string | The source IP address of the client |
| RemoteUser | string | User name supplied with the basic authentication |
| ReqId | string | The randomly generated ID of the request |
| Request | string | Full original request line |
| RequestHeaders | string | Request headers end with 'id' or 'ID' |
| RequestLength | string | Request length in bytes (including request line, header, and request body) |
| RequestTime | real | Time in seconds with millisecond resolution elapsed since the first bytes were read from the client |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string | Response status |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) when the log is collected by Azure Spring Cloud |
| TimeLocal | string | Local time in the common log format |
| Type | string | The name of the table |
| UpstreamAddr | string | The IP address and port (or the path to the domain socket) of the upstream server. If several servers were contacted during request processing, their addresses are separated by commas |
| UpstreamResponseLength | string | The length in bytes of the response obtained from the upstream server |
| UpstreamResponseTime | string | Time spent on receiving the response from the upstream server, the time is kept in seconds with millisecond resolution |
| UpstreamStatus | string | Status code of the response obtained from the upstream server |
