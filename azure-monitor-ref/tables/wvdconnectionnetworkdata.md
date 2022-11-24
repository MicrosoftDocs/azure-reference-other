---
title: Azure Monitor Logs reference - WVDConnectionNetworkData
description: Reference for WVDConnectionNetworkData table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# WVDConnectionNetworkData

 Windows Virtual Desktop connection network data.

## Categories

- Azure Virtual Desktop
## Solutions

- LogManagement
## Resource types

- Desktop Virtualization Host Pools




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CorrelationId | string | The correlation ID for the activity |
| EstAvailableBandwidthKBps | int | The average of estimated network bandwidth (kilobyte per second) in the last evaluated connection time interval |
| EstRoundTripTimeInMs | int | The average of estimated network round trip times (milliseconds) in the last evaluated connection time interval |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) when the network event was generated on the VM |
| Type | string | The name of the table |
