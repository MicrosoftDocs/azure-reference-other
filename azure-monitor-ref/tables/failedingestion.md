---
title: Azure Monitor Logs reference - FailedIngestion
description: Reference for FailedIngestion table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/21/2024
---

# FailedIngestion

Failed ingestion operations logs provide detailed information about failed ingest operations. Logs include data source details, as well as error code and failure status (transient or permanent), that can be used for tracking the process of data source ingestion. Users can identify usage errors (permanent bad requests) and handle retries of transient failures. Ingestion logs are supported for queued ingestion to the ingestion endpoint using SDKs, data connections, and connectors.


## Categories

- Azure Resources

## Solutions

- LogManagement

## Resource types

- Azure Data Explorer Clusters

## Queries

 Sample queries for the [FailedIngestion](/azure/azure-monitor/reference/queries/failedingestion) table.


## Columns
  
[!INCLUDE [failedingestion](.././tables/includes/failedingestion-include.md)]
