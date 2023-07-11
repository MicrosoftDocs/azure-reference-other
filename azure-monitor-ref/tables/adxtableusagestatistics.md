---
title: Azure Monitor Logs reference - ADXTableUsageStatistics
description: Reference for ADXTableUsageStatistics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/10/2023
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
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | The client request id |
| DatabaseName | string | The name of the database |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| MaxCreatedOn | datetime | Lastest extent time of the table |
| MinCreatedOn | datetime | Oldest extent time of the table |
| OperationName | string | The name of this operation |
| Principal | string | The principal that invoked the query |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RootActivityId | string | The root activity id |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| StartedOn | datetime | Time (UTC) at which table usage statistics operation started |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TableName | string | The name of the table |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time (UTC) at which this event was generated |
| Type | string | The name of the table |
| User | string | The user that invoked the query |
