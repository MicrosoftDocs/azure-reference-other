---
title: Azure Monitor Logs reference - WVDConnectionGraphicsDataPreview
description: Reference for WVDConnectionGraphicsDataPreview table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# WVDConnectionGraphicsDataPreview

 Windows Virtual Desktop connection graphics data.

## Categories

- Azure Virtual Desktop
## Solutions

- LogManagement
## Resource types

- Desktop Virtualization Host Pools




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ClientSkippedFramesPercentage | int | The percentage of frames dropped because of slow client decoding in the second with the highest dropped frames in the last evaluated connection time interval |
| CompressedFrameSizeInBytes | int | The compressed size (bytes) of the frame with highest E2E delay in the last evaluated connection time interval |
| CorrelationId | string | The correlation ID for the activity |
| DecodingTimeOnClientInMs | int | The decoding time (milliseconds) of the frame with highest E2E delay in the last evaluated connection time interval |
| EncodingDelayOnServerInMs | int | The encoding time (milliseconds) of the frame with highest E2E delay in the last evaluated connection time interval |
| EndToEndDelayInMs | int | The highest end-to-end delay (milliseconds) of the frames sent in the last evaluated connection time interval. E2E delay is the delay from the time when a frame is captured on the server until the time frame is rendered on the client |
| EstAvailableBandwidthKBps | int | The average of estimated network bandwidth (kilobyte per second) in the last evaluated connection time interval |
| EstRoundTripTimeInMs | int | The average of estimated network round trip times (milliseconds) in the last evaluated connection time interval |
| NetworkSkippedFramesPercentage | int | The percentage of frames dropped because of insufficient network bandwidth in the second with the highest dropped frames in the last evaluated connection time interval |
| RenderingTimeOnClientInMs | int | The rendering time (milliseconds) of the frame with highest E2E delay in the last evaluated connection time interval |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ServerSkippedFramesPercentage | int | The percentage of frames dropped because server is busy in the second with the highest dropped frames in the last evaluated connection time interval |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) when the QoE event was generated on the VM |
| Type | string | The name of the table |
