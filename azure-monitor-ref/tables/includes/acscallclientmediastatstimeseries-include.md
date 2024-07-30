---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ACSCallClientMediaStatsTimeSeries
---


| Column | Type | Description |
|---|---|---|
| AggregationIntervalSeconds | int | ACS calling media stats aggregation interval in seconds. |
| Average | real | The average of a certain media metric statistics. |
| _BilledSize | real | The record size in bytes |
| CallClientTimeStamp | datetime | The timestamp (UTC) of when the ACS client's media stats log was generated. |
| CallId | string | The identifier of the call used to correlate. Can be used to identify correlated events between multiple tables. |
| ClientInstanceId | string | Client instance ID. |
| Count | long | The count of a certain media metric statistics. |
| EndpointId | string | ACS calling endpoint ID. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Maximum | real | The maximum of a certain media metric statistics. |
| MediaStreamCodec | string | Client media stream codec. |
| MediaStreamDirection | string | Client media stream direction, i.e. recv or send. |
| MediaStreamId | string | ACS calling media stream ID. |
| MediaStreamType | string | Client media stream type, i.e. video or screen. |
| MetricName | string | Client metric name. |
| Minimum | real | The minimum of a certain media metric statistics. |
| OperationName | string | The operation associated with log record. |
| ParticipantId | string | ID of the participant. |
| RemoteEndpointId | string | ACS calling remote endpoint ID. |
| RemoteParticipantId | string | ACS remote participant ID. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Sum | real | The sum of a certain media metric statistics. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
