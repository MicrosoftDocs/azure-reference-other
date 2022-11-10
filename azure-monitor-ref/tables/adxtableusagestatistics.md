---
title: Azure Monitor Logs reference - ADXTableUsageStatistics
description: Reference for ADXTableUsageStatistics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# ADXTableUsageStatistics

 Azure Data Explorer table usage statistics.

## Solutions

- LogManagement
## Resource types

- Azure Data Explorer Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationName | string | application name invoked the command |
| CorrelationId | string | The client request id |
| DatabaseName | string | The name of the database |
| MaxCreatedOn | datetime | Lastest extent time of the table |
| MinCreatedOn | datetime | Oldest extent time of the table |
| OperationName | string | The name of this operation |
| Principal | string | The principal that invoked the query |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RootActivityId | string | The root activity id |
| SourceSystem | string |  |
| StartedOn | datetime | Time (UTC) at which table usage statistics operation started |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TableName | string | The name of the table |
| TenantId | string |  |
| TimeGenerated | datetime | The time (UTC) at which this event was generated |
| Type | string | The name of the table |
| User | string | The user that invoked the query |
