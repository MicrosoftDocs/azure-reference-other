---
title: Azure Monitor Logs reference - SignalRServiceDiagnosticLogs
description: Reference for SignalRServiceDiagnosticLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# SignalRServiceDiagnosticLogs

 Azure SignalR Service Diagnostic Logs

## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime|The timestamp (UTC) of the log|
|OperationName|string||
|Location|string|Location of Azure SignalR Service|
|Level|string|Log level|
|CallerIpAddress|string|Caller Ip address|
|Message|string|Log message|
|UserId|string|User ID for the connection|
|ConnectionId|string|Connection ID|
|ConnectionType|string|Connection type|
|TransportType|string|Transport type|
|Type|string||
|_ResourceId|string||
