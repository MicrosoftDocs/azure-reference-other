---
title: Azure Monitor Logs reference - SynapseDXFailedIngestion
description: Reference for SynapseDXFailedIngestion table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# SynapseDXFailedIngestion

 Failed ingestion operations logs provide detailed information about failed ingest operations. Logs include data source details, as well as error code and failure status (transient or permanent), that can be used for tracking the process of data source ingestion. Users can identify usage errors (permanent bad requests) and handle retries of transient failures. Ingestion logs are supported for queued ingestion to the ingestion endpoint using SDKs, data connections, and connectors

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
| Details | string | Details of the failure |
| ErrorCode | string | Failure's error code like 'BadRequest_EmptyBlob' |
| FailedOn | datetime | The time this ingest operation failed |
| FailureStatus | string | Failure's status like 'Permanent' |
| IngestionSourceId | string | The ID of the ingestion source |
| IngestionSourcePath | string | Azure blob storage URI |
| OperationId | string | The ingestion's operation ID |
| OriginatesFromUpdatePolicy | bool | Indicates if the failure originates from an Update Policy |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | Final state of this data ingestion operation like 'Failed' |
| RootActivityId | string | The ingestion's activity ID Used for debugging issues |
| ShouldRetry | bool | Indicates if the failure is temporary and the operation should be retried |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Table | string | The name of the target table the data is ingested into |
| TenantId | string |  |
| TimeGenerated | datetime | The time (UTC) when this event was generated |
| Type | string | The name of the table |
