---
title: Azure Monitor Logs reference - REDConnectionEvents
description: Reference for REDConnectionEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/2/2023
---

# REDConnectionEvents

 Logs the connection events when client connects to redis enterprise database.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ClientIp | string | The Redis client IP address. |
| ConnectionId | long | Unique connection ID assigned by Redis. |
| EventEpochTime | long | The unix timestamp (number of seconds since January 1, 1970) when the event happened in UTC. This can be converted to datetime format using function unixtime_seconds_todatetime in log analytics workspace. |
| EventStatus | int | Results of an authentication request as a status code (only applicable for authentication event). |
| EventType | string | Type of connection event(new_conn/auth/close_conn). |
| Location | string | The location (i.e. region) of the Azure Cache for Redis Enterprise instance that was accessed. |
| OperationName | string | The Redis operation associated with the log record. |
| PrivateLinkIPv6 | string | The Redis client private link IPv6 address (if applicable). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) when event audit log was captured. |
| Type | string | The name of the table |
