---
title: Azure Monitor Logs reference - AppPlatformIngressLogs
description: Reference for AppPlatformIngressLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# AppPlatformIngressLogs

 Azure Spring Cloud ingress logs, currently it is nginx access logs.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Spring Cloud




## Columns

| Column | Type | Description |
| --- | --- | --- |
| BodyBytesSent | string | Number of bytes sent to a client, not counting the response header |
| Host | string | The host name of the log |
| HttpReferer | string | Value of the referer header |
| HttpUserAgent | string | Value of user-agent header |
| OperationName | string | The name of the operation represented by this event |
| ProxyAlternativeUpstreamName | string | Name of the alternative upstream server. The format is upstream-&lt;namespace&gt;-&lt;service name&gt;-&lt;service port&gt; |
| ProxyUpstreamName | string | Name of the upstream server. The format is upstream-&lt;namespace&gt;-&lt;service name&gt;-&lt;service port&gt; |
| RemoteAddr | string | The source IP address of the client |
| RemoteUser | string | User name supplied with the basic authentication |
| ReqId | string | The randomly generated ID of the request |
| Request | string | Full original request line |
| RequestHeaders | string | Request headers end with 'id' or 'ID' |
| RequestLength | string | Request length in bytes (including request line, header, and request body) |
| RequestTime | real | Time in seconds with millisecond resolution elapsed since the first bytes were read from the client |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| Status | string | Response status |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) when the log is collected by Azure Spring Cloud |
| TimeLocal | string | Local time in the common log format |
| Type | string | The name of the table |
| UpstreamAddr | string | The IP address and port (or the path to the domain socket) of the upstream server. If several servers were contacted during request processing, their addresses are separated by commas |
| UpstreamResponseLength | string | The length in bytes of the response obtained from the upstream server |
| UpstreamResponseTime | string | Time spent on receiving the response from the upstream server, the time is kept in seconds with millisecond resolution |
| UpstreamStatus | string | Status code of the response obtained from the upstream server |
