---
title: Azure Monitor Logs reference - WUDOStatus
description: Reference for WUDOStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# WUDOStatus

 

## Categories

- Desktop Analytics
## Solutions

- Update Compliance




## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string||
|TimeGenerated|datetime||
|Computer|string||
|ComputerID|string||
|GroupID|string||
|OSName|string||
|OSVersion|string||
|DownloadMode|string||
|DownloadModeSrc|string||
|ContentDownloadMode|int||
|DOStatusDescription|string||
|Country|string||
|City|string||
|ISP|string||
|PeeringStatus|string||
|ContentType|string||
|TotalTimeForDownload|string||
|TotalTransfers|long||
|PeerEligibleTransfers|long||
|NoPeersCount|long||
|PeersUnknownCount|long||
|PeersSuccessCount|long||
|PeersCannotConnectCount|long||
|BytesFromCDN|long||
|BytesFromIntPeers|long||
|BytesFromPeers|long||
|BytesFromGroupPeers|long||
|BWOptPercent7Days|real||
|BWOptPercent28Days|real||
|LastScan|datetime||
|Type|string||
