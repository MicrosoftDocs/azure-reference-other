---
title: Azure Monitor Logs reference - CDBQueryRuntimeStatistics
description: Reference for CDBQueryRuntimeStatistics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# CDBQueryRuntimeStatistics

 This table details query operations executed against a SQL API account. By default, the query text and its parameters are obfuscated to avoid logging PII data with full text query logging available by request.

## Solutions

- LogManagement
## Resource types

- Azure Cosmos DB




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccountName | string | The name of the Cosmos DB account against which the query operation was issued. |
| ActivityId | string | The unique identifier (GUID) for this query operation, which can be correlating with the CDBDataPlaneRequests table for additional debugging. |
| CollectionName | string | The name of the Cosmos DB container against which this query was issued. |
| DatabaseName | string | The name of the Cosmos DB database containing the Cosmos DB container against which this query was issued. |
| PartitionKeyRangeId | string | The physical partition to which this query was issued. |
| QueryText | string | The query text (obfuscated by default, full query string provided upon request) for the operation. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (in UTC) when this query operation was executed. |
| Type | string | The name of the table |
