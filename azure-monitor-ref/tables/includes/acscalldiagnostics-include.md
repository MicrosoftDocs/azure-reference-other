---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ACSCallDiagnostics
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The log category of the event. Logs with the same log category and resource type will have the same properties fields. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| EndpointId | string | ID of the endpoint. |
| EndpointType | string | Type of the endpoint. |
| HealedDataRatioAvg | real | Average healed data ratio for incoming audio. |
| HealedDataRatioMax | real | Maximum healed data ratio for incoming audio. |
| Identifier | string | The indentifier of the call used to correlate. Can be used to identify correlated events between multiple tables. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| JitterAvg | int | Average delay of sending the packages in milliseconds. |
| JitterBufferSizeAvg | int | Average jitter buffer size in milliseconds. |
| JitterBufferSizeMax | int | Maximum jitter buffer size in milliseconds. |
| JitterMax | int | Max delay of sending the packages in milliseconds. |
| MediaType | string | Type of Media. |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API-version associated with the operation or version of the operation (if there is no API version). |
| PacketLossRateAvg | real | Average lost packages. |
| PacketLossRateMax | real | Max lost packages. |
| ParticipantId | string | ID of the participant. |
| RecvFreezeDurationPerMinuteInMs | real | Average receive freeze duration per minute in microseconds. |
| RecvResolutionHeight | int | Receive average resolution height. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RoundTripTimeAvg | int | Average time of a round trip in milliseconds. |
| RoundTripTimeMax | int | Max time of a trip in milliseconds. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StreamId | long | ID of the stream. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| TransportType | string | Type of the internet transport layer, it can be UDP, TCP or unknown. |
| Type | string | The name of the table |
| VideoFrameRateAvg | real | Average frames per second. |
