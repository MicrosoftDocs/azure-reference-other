---
title: Azure Monitor Logs reference - SynapseDXIngestionBatching
description: Reference for SynapseDXIngestionBatching table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# SynapseDXIngestionBatching

 Azure data explore synapse ingestion batching operations. These logs have detailed statistics of batches ready for ingestion (duration, batch size and blobs count)

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Synapse Workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| BatchingType | string | Batching type: Whether the batch reached the limit of batching time, data size, or number of files set by the the batching policy |
| BatchSizeBytes | long | Total uncompressed size of data in this batch (bytes) |
| BatchTimeSeconds | real | Total batching time of this batch (seconds) |
| Database | string | The name of the database holding the target table |
| DataSourcesInBatch | int | Number of data sources in this batch |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RootActivityId | string | The operation's activity ID |
| SourceCreationTime | datetime | When the first blobs in this batch were created (UTC time) |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Table | string | The name of the target table the data is ingested into |
| TenantId | string |  |
| TimeGenerated | datetime | The time (UTC) this event was generated |
| Type | string | The name of the table |
