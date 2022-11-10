---
title: Azure Monitor Logs reference - SignalRServiceDiagnosticLogs
description: Reference for SignalRServiceDiagnosticLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# SignalRServiceDiagnosticLogs

 Azure SignalR service diagnostic logs.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- SignalR




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallerIpAddress | string | The IP of the client or server connects to SignalR service. |
| Collection | string | The collection of the log event. Can be 'Connection', 'Authorization', 'Throttling' or 'Message'. 'Connection' collection includes the logs about the lifetime of connections. 'Authorization' includes the logs about the authorization of connections. 'Throttling' includes the logs about the throttled connections. 'Message' includes the logs about the tracing messages. |
| ConnectionId | string | The connection ID of the connection connected to SignalR service. |
| ConnectionType | string | The connection type. Can be 'Server' and 'Client'. 'Server' means the connection connects to an app server. 'Client' means the connection connects to a SignalR client. |
| GroupName | string | A group can have any number of clients, and a client can be a member of any number of groups. |
| HubName | string | The SignalR Hubs API enables you to call methods on connected clients from the server. |
| InvocationId | string | The invocation ID of the message. It's only available in ASP.NET SignalR. |
| Level | string | The level of the log. Can be 'Informational', 'Warning', 'Error' or 'Critical'. |
| Location | string | The location of Azure SignalR service. |
| Message | string | The message of the log event. It describes the log event in detail. |
| MessageTracingId | long | The tracing ID of the message. It's used for tracing messages. |
| MessageType | string | The type of the messsage. Can be 'BroadcastDataMessage', 'MultiConnectionDataMessage', 'GroupBroadcastDataMessage', 'MultiGroupBroadcastDataMessage', 'UserDataMessage', 'MultiUserDataMessage', 'JoinGroupWithAckMessage' and 'LeaveGroupWithAckMessage'. For more details, see https://www.nuget.org/packages/Microsoft.Azure.SignalR.Protocols. |
| OperationName | string | The operation name of the log event. it can be used to filter the log based on a specific operation name. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the log. |
| TransportType | string | The transport type of the connection. Can be 'WebSockets', 'ServerSentEvents', or 'LongPolling'. For more details, see https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.http.connections.httptransporttype. |
| Type | string | The name of the table |
| UserId | string | The user ID of the connection. It is defined by the client or app server. |
