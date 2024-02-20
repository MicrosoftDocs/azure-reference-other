---
title: Azure Monitor Logs reference - SynapseDXFailedIngestion
description: Reference for SynapseDXFailedIngestion table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024
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
  
[!INCLUDE [synapsedxfailedingestion](.././tables/includes/synapsedxfailedingestion-include.md)]
