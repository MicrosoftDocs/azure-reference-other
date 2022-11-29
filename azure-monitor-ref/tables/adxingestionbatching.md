---
title: Azure Monitor Logs reference - ADXIngestionBatching
description: Reference for ADXIngestionBatching table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# ADXIngestionBatching

 Azure Data Explorer ingestion batching operations. These logs have detailed statistics of batches ready for ingestion (duration, batch size and blobs count).

## Solutions

- LogManagement
## Resource types

- Azure Data Explorer Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| BatchingType | string | Type of batching: whether the batch reached batching time, data size or number of files limit set by batching policy |
| BatchSizeBytes | long | Total uncompressed size of data in this batch (bytes) |
| BatchTimeSeconds | real | Total batching time of this batch (seconds) |
| Database | string | Name of the database holding the target table |
| DataSourcesInBatch | int | Number of data sources in this batch |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RootActivityId | string | The operation's activity Id |
| SourceCreationTime | datetime | Minimal time (UTC) at which blobs in this batch were created |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Table | string | Name of the target table into which the data is ingested |
| TenantId | string |  |
| TimeGenerated | datetime | The time (UTC) at which this event was generated |
| Type | string | The name of the table |
