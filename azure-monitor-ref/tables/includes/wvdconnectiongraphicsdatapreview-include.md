---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: WVDConnectionGraphicsDataPreview
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClientSkippedFramesPercentage | int | The percentage of frames dropped because of slow client decoding in the second with the highest dropped frames in the last evaluated connection time interval |
| CompressedFrameSizeInBytes | int | The compressed size (bytes) of the frame with highest E2E delay in the last evaluated connection time interval |
| CorrelationId | string | The correlation ID for the activity |
| DecodingTimeOnClientInMs | int | The decoding time (milliseconds) of the frame with highest E2E delay in the last evaluated connection time interval |
| EncodingDelayOnServerInMs | int | The encoding time (milliseconds) of the frame with highest E2E delay in the last evaluated connection time interval |
| EndToEndDelayInMs | int | The highest end-to-end delay (milliseconds) of the frames sent in the last evaluated connection time interval. E2E delay is the delay from the time when a frame is captured on the server until the time frame is rendered on the client |
| EstAvailableBandwidthKBps | int | The average of estimated network bandwidth (kilobyte per second) in the last evaluated connection time interval |
| EstRoundTripTimeInMs | int | The average of estimated network round trip times (milliseconds) in the last evaluated connection time interval |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| NetworkSkippedFramesPercentage | int | The percentage of frames dropped because of insufficient network bandwidth in the second with the highest dropped frames in the last evaluated connection time interval |
| RenderingTimeOnClientInMs | int | The rendering time (milliseconds) of the frame with highest E2E delay in the last evaluated connection time interval |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ServerSkippedFramesPercentage | int | The percentage of frames dropped because server is busy in the second with the highest dropped frames in the last evaluated connection time interval |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) when the QoE event was generated on the VM |
| Type | string | The name of the table |
