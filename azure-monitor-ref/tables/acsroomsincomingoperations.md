---
title: Azure Monitor Logs reference - ACSRoomsIncomingOperations
description: Reference for ACSRoomsIncomingOperations table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# ACSRoomsIncomingOperations

 Communication Services logs of incoming requests to rooms operations, with summaries of room object, lifespan, participants and roles count etc.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Communication Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CorrelationId | string | The ID of the room, which is a distinguished identifier for an existing room. |
| Level | string | The severity level of the operation. |
| OperationName | string | The operation associated with log record. e.g., CreateRoom, PatchRoom, GetRoom, DeleteRoom, GetParticipants, AddParticipants, UpdateParticipants, or RemoveParticipants |
| OperationVersion | string | The API-version associated with the operation or version of the operation (if there is no API version). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | string | The sub status of the operation. If this operation corresponds to a REST API call, this field is the HTTP status code of the corresponding REST call. |
| ResultType | string | The status of the operation. |
| RoomJoinPolicy | string | The policy of a room indicating invite only or CommunicationServiceUsers. |
| RoomLifespan | int | The Room lifespan in minutes. |
| RoomParticipantsAttendee | int | The participants count with attendee role. |
| RoomParticipantsConsumer | int | The participants count with consumer role. |
| RoomParticipantsCount | int | The count of participants in a room. |
| RoomParticipantsPresenter | int | The participants count with presenter role. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
