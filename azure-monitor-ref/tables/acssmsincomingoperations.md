---
title: Azure Monitor Logs reference - ACSSMSIncomingOperations
description: Reference for ACSSMSIncomingOperations table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# ACSSMSIncomingOperations

 Communication Services logs of incoming requests to SMS operations.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Communication Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallerIpAddress | string | The caller IP address, if the operation corresponds to an API call that would come from an entity with a publicly available IP address. |
| Category | string | The log category of the event. Logs with the same log category and resource type will have the same properties fields. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| DeliveryAttempts | int | The number of attempts made to deliver this message. |
| DurationMs | int | The duration of the operation in milliseconds. |
| IncomingMessageLength | int | The number of characters in the incoming message. |
| Level | string | The severity level of the operation. |
| Method | string | The method used in the request. |
| NumberType | string | The type of number used for sending or receiving the SMS message (e.g. LongCodeNumber) |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API-version associated with the operation or version of the operation (if there is no API version). |
| OutgoingMessageLength | int | The number of characters in the outgoing message. |
| PhoneNumber | string | The number used for sending or receiving the SMS message (e.g. +18445791704) |
| PlatformType | string | The platform type being used in the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | The status text response of the result of this operation. |
| ResultSignature | string | The sub status of the operation. If this operation corresponds to a REST API call, this field is the HTTP status code of the corresponding REST call. |
| ResultType | string | The status of the operation. |
| SdkType | string | The SDK type being used in the request. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| URI | string | The URI of the request. |
