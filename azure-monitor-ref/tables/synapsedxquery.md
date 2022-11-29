---
title: Azure Monitor Logs reference - SynapseDXQuery
description: Reference for SynapseDXQuery table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# SynapseDXQuery

 Azure data explorer synpase query execution summary. Logs include DatabaseName, State, Duration that can be used for monitoring the queries which were invoked on the cluster

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Synapse Workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationName | string | The name of the application that invoked the query |
| CacheDiskHits | long | Disk cache hits |
| CacheDiskMisses | long | Disk cache misses |
| CacheMemoryHits | long | Memory cache hits |
| CacheMemoryMisses | long | Memory cache misses |
| CacheShardsBypassBytes | long | Shards cache bypass bytes |
| CacheShardsColdHits | long | Shards cold cache hits |
| CacheShardsColdMisses | long | Shards cold cache misses |
| CacheShardsHotHits | long | Shards hot cache hits |
| CacheShardsHotMisses | long | Shards hot cache misses |
| Category | string | The log category for these events will be 'Query' |
| CorrelationId | string | The client request ID |
| DatabaseName | string | The name of the database the command ran on |
| Duration | string | Query duration as a string like '00:00:00.0156250' |
| ExtentsMaxDataScannedTime | datetime | Maximum data scan time |
| ExtentsMinDataScannedTime | datetime | Minimum data scan time |
| FailureReason | string | The reason for the failure |
| LastUpdatedOn | datetime | The time (UTC) this command ended |
| MemoryPeak | long | Memory peak |
| Principal | string | The principal that invoked the query like 'aaduser=USER_ID;TENANT' |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RootActivityId | string | The root activity ID |
| ScannedExtentsCount | long | Scanned extents count |
| ScannedRowsCount | long | Scanned rows count |
| SourceSystem | string |  |
| StartedOn | datetime | The time (UTC) this command started |
| State | string | The state the command ended with like 'Completed' |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TableCount | int | Table count |
| TablesStatistics | dynamic | Tables statistics |
| TenantId | string |  |
| Text | string | Text of the invoked query |
| TimeGenerated | datetime | The time (UTC) this event was generated |
| TotalCPU | string | Total CPU runtime across cluster nodes |
| TotalExtentsCount | long | Total extents count |
| TotalRowsCount | long | Total rows count |
| Type | string | The name of the table |
| User | string | User that invoked the query |
| WorkloadGroup | string | Workload are a means of resource governance for incoming requests to the cluster |
