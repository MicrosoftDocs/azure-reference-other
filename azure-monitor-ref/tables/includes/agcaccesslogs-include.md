---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AGCAccessLogs
---


| Column | Type | Description |
|---|---|---|
| BackendHost | string | Address of backend target with appended port. For example \<ip\>:\<port\> |
| BackendIp | string | IP address of backend target Application Gateway for Containers proxies the request to. |
| BackendPort | int | Port number of the backend target. |
| BackendResponseLatency | real | Time in milliseconds to receive first byte from Application Gateway for Containers to the backend target. |
| BackendTimeTaken | int | Time in milliseconds for the response to be transmitted from the backend target to Application Gateway for Containers. |
| _BilledSize | real | The record size in bytes |
| ClientIp | string | IP address of the client initiating the request to the frontend of Application Gateway for Containers. |
| FrontendName | string | Name of the Application Gateway for Containers frontend that received the request from the client. |
| FrontendPort | int | Port number the request was listened on by Application Gateway for Containers. |
| HostName | string | Host header value received from the client by Application Gateway for Containers. |
| HttpMethod | string | HTTP Method of the request received from the client by Application Gateway for Containers as per RFC 7231. |
| HttpStatusCode | int | HTTP Status code returned from Application Gateway for Containers to the client. |
| HttpVersion | string | HTTP version of the request received from the client by Application Gateway for Containers. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | Name of the operation. |
| Referrer | string | Referrer header of the request received from the client by Application Gateway for Containers. |
| Region | string | The region where Application Gateway for Containers association is deployed |
| RequestBodyBytes | long | Size in bytes of the body payload of the request received from the client by Application Gateway for Containers. |
| RequestHeaderBytes | long | Size in bytes of the headers of the request received from the client by Application Gateway for Containers. |
| RequestUri | string | URI of the request received from the client by Application Gateway for Containers (everything after \<protocol\>://\<host\> of the URL). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseBodyBytes | long | Size in bytes of the body payload of the response returned to the client by Application Gateway for Containers. |
| ResponseHeaderBytes | long | Size in bytes of the headers of the response returned to the client by Application Gateway for Containers. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time (UTC) when the log was created. |
| TimeTaken | real | Time in milliseconds of the client request received by Application Gateway for Containers and the last byte returned to the client from Application Gateway for Containers. |
| TlsCipher | string | TLS cipher suite negotiated between the client and Application Gateway for Containers frontend. |
| TlsProtocol | string | TLS version negotiated between the client and Application Gateway for Containers frontend. |
| TrackingId | string | Generated guid by Application Gateway for Containers to help with tracking and debugging. This value correlates to the x-request-id header returned to the client from Application Gateway for Containers. |
| Type | string | The name of the table |
| UserAgent | string | User-Agent header of the request received from the client by Application Gateway for Containers. |
