---
title: Azure Monitor Logs reference - SignalRServiceDiagnosticLogs
description: Reference for SignalRServiceDiagnosticLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# SignalRServiceDiagnosticLogs

 Azure SignalR Service Diagnostic Logs

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- SignalR




## Columns

|Column|Type|Description|
|---|---|---|
|CallerIpAddress|string|Caller Ip address|
|ConnectionId|string|Connection ID|
|ConnectionType|string|Connection type|
|Level|string|Log level|
|Location|string|Location of Azure SignalR Service|
|Message|string|Log message|
|OperationName|string||
|_ResourceId|string||
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of the log|
|TransportType|string|Transport type|
|Type|string||
|UserId|string|User ID for the connection|
