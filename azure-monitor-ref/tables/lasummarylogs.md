---
title: Azure Monitor Logs reference - LASummaryLogs
description: Reference for LASummaryLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# LASummaryLogs

Provides Summary logs rules execution details, including run status, duration and errors. Can be used to view bins executions statuses, identify rules that take a long time to complete, and failures that could be optimized in query, or shorted bin time.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.operationalinsights/workspaces|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/lasummarylogs)|



## Columns
  
[!INCLUDE [lasummarylogs](.././tables/includes/lasummarylogs-include.md)]
