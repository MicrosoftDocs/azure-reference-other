---
title: Azure Monitor Logs reference - ACSNetworkTraversalDiagnostics
description: Reference for ACSNetworkTraversalDiagnostics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# ACSNetworkTraversalDiagnostics

 Diagnostics logs provide information about the relay session connectivity and the data relayed.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Communication Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| BytesReceived | long | Number of bytes received by the client. |
| BytesSent | long | Number of bytes sent by the client. |
| CallerIpAddress | string | The caller IP address, if the operation corresponds to an API call that would come from an entity with a publicly available IP address. |
| Category | string | The log category of the event. Logs with the same log category and resource type will have the same properties fields. |
| CorrelationId | string | The ID associated with the relay session. |
| Identity | string | The request sender's identity, if provided when requesting the relay configuration used to establish the session. |
| Level | string | The severity level of the operation. |
| OperationName | string | The operation associated with log record. |
| Protocol | string | The protocol used for the session (e.g. TCP or UDP). |
| Reason | string | Describes the reason for the relay session ending (e.g. Deallocated or Expired). Only defined for logs of the operation RelaySessionEnd. |
| RelayLocation | string | The location of the relay server. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | string | The sub status of the operation. If this operation corresponds to a REST API call, this field is the HTTP status code of the corresponding REST call. |
| ResultType | string | The status of the operation (e.g. Succeeded or Failed). |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| TotalBytesFromClient | long | Number of bytes received from a client during the session. |
| TotalBytesToClient | long | Number of bytes sent to a client during the session. |
| Type | string | The name of the table |
