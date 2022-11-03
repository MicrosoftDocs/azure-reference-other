---
title: Azure Monitor Logs reference - SynapseDXSucceededIngestion
description: Reference for SynapseDXSucceededIngestion table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# SynapseDXSucceededIngestion

 Succeeded ingestion operations logs provide information about successfully completed ingest operations. Logs include data source details that together with `Failed ingestion operations` logs can be used for tracking the process of ingestion of each data source. Ingestion logs are supported for queued ingestion to the ingestion endpoint using SDKs, data connections, and connectors

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Synapse Workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Database | string | The name of the database holding the target table |
| IngestionSourceId | string | The ingestion source ID |
| IngestionSourcePath | string | Azure blob storage URI |
| OperationId | string | The ingestion's operation ID |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | Final state of this data ingestion operation like 'Succeeded' |
| RootActivityId | string | The ingestion's activity ID |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SucceededOn | datetime | The time this ingest operation ended successfully |
| Table | string | The name of the target table the data is ingested into |
| TenantId | string |  |
| TimeGenerated | datetime | The time (UTC) when this event was generated |
| Type | string | The name of the table |
