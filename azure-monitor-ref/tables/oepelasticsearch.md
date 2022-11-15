---
title: Azure Monitor Logs reference - OEPElasticsearch
description: Reference for OEPElasticsearch table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# OEPElasticsearch

 Diagnostic logs for Elasticsearch cluster. It could be slow logs, server logs or deprecation logs.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Microsoft.OpenEnergyPlatform/energyServices




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | Logs generated as a result of operations executed using OAK APIs are grouped into categories. Categories in OAK are logical groupings based on the data source. |
| Content | string | Log details as a result of operation performed. |
| Duration | string | Time taken for performing the operation. Value is taken from 'took' property in Elasticsearch cluster as string, like '1.3ms', '478.9micros' etc. |
| Location | string | The region of the resource emitting the event. |
| Namespace | string | Namespace from which logs were generated, represents the data partition. |
| OperationName | string | The operation name for which the log entry was created. |
| PodName | string | Elasticsearch pod name. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Source | string | Source responsible for the log. It could be a search query or a record to be indexed in case of slow logs and null otherwise. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (in UTC) when the log was created. |
| TotalHits | string | Total number of hits for a search operation. For example, value can be '3 hits' for 3 hits, '-1' for no hits, or 'null' if it is not a search slow log. |
| Type | string | Type of log. Can be index_search_slowlog, index_indexing_slowlog, server, deprecation etc. |
