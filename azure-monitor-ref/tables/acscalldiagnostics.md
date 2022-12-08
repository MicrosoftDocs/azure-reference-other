---
title: Azure Monitor Logs reference - ACSCallDiagnostics
description: Reference for ACSCallDiagnostics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# ACSCallDiagnostics

 Diagnostics logs provide information about the media transfers that occur in a call. Every log corresponds to an individual media stream and contains information about the emitting endpoint (e.g. the user sending the stream).

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Communication Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | The log category of the event. Logs with the same log category and resource type will have the same properties fields. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| EndpointId | string | ID of the endpoint. |
| EndpointType | string | Type of the endpoint. |
| Identifier | string | The indentifier of the call used to correlate. Can be used to identify correlated events between multiple tables. |
| JitterAvg | int | Average delay of sending the packages in milliseconds. |
| JitterMax | int | Max delay of sending the packages in milliseconds. |
| MediaType | string | Type of Media. |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API-version associated with the operation or version of the operation (if there is no API version). |
| PacketLossRateAvg | real | Average lost packages. |
| PacketLossRateMax | real | Max lost packages. |
| ParticipantId | string | ID of the participant. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RoundTripTimeAvg | int | Average time of a round trip in milliseconds. |
| RoundTripTimeMax | int | Max time of a trip in milliseconds. |
| SourceSystem | string |  |
| StreamId | long | ID of the stream. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| TransportType | string | Type of the internet transport layer, it can be UDP, TCP or unknown. |
| Type | string | The name of the table |
