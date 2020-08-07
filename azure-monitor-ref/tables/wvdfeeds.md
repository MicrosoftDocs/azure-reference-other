---
title: Azure Monitor Logs reference - WVDFeeds
description: Reference for WVDFeeds table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 7/30/2020
---

# WVDFeeds

 Windows Virtual Desktop Feed Activity

## Categories

- Windows Virtual Desktop
## Solutions

- LogManagement
## Resource types

- Desktop Virtualization workspaces




## Columns

|Column|Type|Description|
|---|---|---|
|ClientOS|string|The OS of the client that is requesting the feed (if available).|
|ClientType|string|The type of the client that is requesting the feed (if available).|
|ClientVersion|string|The version of the client that is requesting the feed (if available).|
|CorrelationId|string|The activity Id.|
|IconFail|int|The number of Icons (PNG, ICO) files that failed to be retrieved.|
|IconTotal|int|The total number of Icons (PNG, ICO) files that the client attempted to retrieve.|
|RDPFail|int|The number of RDP files that failed to be retrieved.|
|RDPTotal|int|The total number of RDP files that the client attempted to retrieve.|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of the event.|
|Type|string|The name of the table|
|UserName|string|The user that initiated the feed request.|
