---
title: Azure Monitor Logs reference - WVDConnections
description: Reference for WVDConnections table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# WVDConnections

 Windows Virtual Desktop Connection Activity

## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|ClientIPAddress|string|The IP address of the client.|
|ClientOS|string|The OS of the client that is connecting (if available).|
|ClientType|string|The type of the client that is connecting (if available).|
|ClientVersion|string|The version of the client that is connecting (if available).|
|ConnectionType|string|The type of connection - either RAIL (RemoteApp Integrated Locally) or Desktop.|
|CorrelationId|string|The activity Id.|
|PredecessorConnectionId|string|The predecessor Correlation Id of the connection, if the current connection is an auto-reconnect.|
|ResourceAlias|string|The alias of the app that the user attempted to connect to.|
|_ResourceId|string||
|SessionHostAgentVersion|string|The version of the WVD Agent running on the machine where the user connection was orchestrated.|
|SessionHostIPAddress|string|The IP address of the machine where the user connection was orchestrated.|
|SessionHostName|string|The FQDN of the machine where the user connection was orchestrated.|
|SessionHostOSDescription|string|The OS SKU description of the machine where the user connection was orchestrated.|
|SessionHostOSVersion|string|The OS version of the machine where the user connection was orchestrated.|
|SessionHostSxSStackVersion|string|The version of the WVD RDP Stack running on the machine where the user connection was orchestrated.|
|SourceSystem|string||
|State|string|The state of the connection.|
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of the event.|
|Type|string||
|UserName|string|The user who initiated the connection.|
