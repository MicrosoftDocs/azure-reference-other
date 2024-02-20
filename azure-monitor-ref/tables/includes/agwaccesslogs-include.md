---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AGWAccessLogs
---


| Column | Type | Description |
|---|---|---|
| BackendPoolName | string | The backend pool associated with the given request log. |
| BackendSettingName | string | The backend setting name associated with the given request log. |
| _BilledSize | real | The record size in bytes |
| ClientIp | string | IP of the immediate client of Application Gateway. If another proxy fronts your application gateway, this displays the IP of that fronting proxy. |
| ClientResponseTime | real | Time difference (in seconds) between first byte received from the backend to first byte sent to the client. |
| Host | string | Address listed in the host header of the request. If rewritten using header rewrite, this field contains the updated host name. |
| HttpMethod | string | HTTP method used by the request. |
| HttpStatus | int | HTTP status code returned to the client from Application Gateway. |
| HttpVersion | string | HTTP version of the request. |
| InstanceId | string | Application Gateway instance that served the request. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ListenerName | string | The listener associated with given request log. |
| OperationName | string | Name of the operation. |
| OriginalHost | string | This field contains the original request host name. |
| OriginalRequestUriWithArgs | string | This field contains the original request URL. |
| ReceivedBytes | int | Size of packet received, in bytes. |
| RequestUri | string | URI of the received request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RuleName | string | The rule associated with the given request log. |
| SentBytes | int | Size of packet sent, in bytes. |
| ServerResponseLatency | real | Latency of the response (in seconds) from the backend server. |
| ServerRouted | string | The backend server that application gateway routes the request to. |
| ServerStatus | int | HTTP status code of the backend server. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SslCipher | string | Cipher suite being used for TLS communication (if TLS is enabled). |
| SslEnabled | string | Whether communication to the backend pools used TLS. Valid values are on and off. |
| SslProtocol | string | SSL/TLS protocol being used (if TLS is enabled). |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time (UTC) when the log was created. |
| TimeTaken | real | Length of time (in seconds) that it takes for the first byte of a client request to be processed and its last-byte sent in the response to the client. It's important to note that the Time-Taken field usually includes the time that the request and response packets are traveling over the network. |
| TransactionId | string | Unique identifier to correlate the request received from the client. |
| Type | string | The name of the table |
| UpstreamSourcePort | int | The source port used by Application Gateway when initiating a connection to the backend target. |
| UserAgent | string | User agent from the HTTP request header. |
| WafEvaluationTime | real | Length of time (in seconds) that it takes for the request to be processed by the WAF. |
| WafMode | string | Value can be either Detection or Prevention. |
