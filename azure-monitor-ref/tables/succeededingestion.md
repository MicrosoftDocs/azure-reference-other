---
title: Azure Monitor Logs reference - SucceededIngestion
description: Reference for SucceededIngestion table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# SucceededIngestion

 Succeeded ingestion operations logs provide information about successfully completed ingest operations. Logs include data source details that together with `Failed ingestion operations` logs can be used for tracking the process of ingestion of each data source. Ingestion logs are supported for queued ingestion to the ingestion endpoint using SDKs, data connections, and connectors.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Data Explorer Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Database | string | The name of the database holding the target table |
| IngestionSourceId | string | A unique identifier representing the ingested source |
| IngestionSourcePath | string | The Azure blob storage URI |
| OperationId | string | The ingestion's operation Id |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The final state of this data ingestion operation |
| RootActivityId | string | The ingestion's activity Id |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SucceededOn | datetime | Time at which this ingest operation successfully ended |
| Table | string | The name of the target table into which the data is ingested |
| TenantId | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
