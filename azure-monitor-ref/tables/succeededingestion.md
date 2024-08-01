---
title: Azure Monitor Logs reference - SucceededIngestion
description: Reference for SucceededIngestion table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# SucceededIngestion

Succeeded ingestion operations logs provide information about successfully completed ingest operations. Logs include data source details that together with `Failed ingestion operations` logs can be used for tracking the process of ingestion of each data source. Ingestion logs are supported for queued ingestion to the ingestion endpoint using SDKs, data connections, and connectors.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.kusto/clusters|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/succeededingestion)|



## Columns
  
[!INCLUDE [succeededingestion](./includes/succeededingestion-include.md)]
