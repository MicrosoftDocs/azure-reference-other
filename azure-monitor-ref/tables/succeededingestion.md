---
title: Azure Monitor Logs reference - SucceededIngestion
description: Reference for SucceededIngestion table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/21/2024
---

# SucceededIngestion

Succeeded ingestion operations logs provide information about successfully completed ingest operations. Logs include data source details that together with `Failed ingestion operations` logs can be used for tracking the process of ingestion of each data source. Ingestion logs are supported for queued ingestion to the ingestion endpoint using SDKs, data connections, and connectors.


## Categories

- Azure Resources

## Solutions

- LogManagement

## Resource types

- Azure Data Explorer Clusters

## Queries

 Sample queries for the [SucceededIngestion](/azure/azure-monitor/reference/queries/succeededingestion) table.


## Columns
  
[!INCLUDE [succeededingestion](.././tables/includes/succeededingestion-include.md)]
