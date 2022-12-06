---
title: Azure Monitor Logs reference - ACRConnectedClientList
description: Reference for ACRConnectedClientList table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# ACRConnectedClientList

 Logs count of Redis clients connected to a cache instance and their IP addresses, logged at a 10-second interval.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Azure Cache for Redis




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CacheName | string | The name of the Azure Cache for Redis instance. |
| ClientCount | int | The number of Redis client connections from the associated IP address. |
| ClientIp | string | The Redis client IP address. |
| Location | string | The location (region) the Azure Cache for Redis instance was accessed in. |
| OperationName | string | The Redis operation associated with the log record. |
| PrivateLinkIpv6 | string | The Redis client private link IPv6 address (if applicable). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RoleInstance | string | The role instance which logged the client list. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp of when the log was generated in UTC. |
| Type | string | The name of the table |
