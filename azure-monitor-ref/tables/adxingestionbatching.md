---
title: Azure Monitor Logs reference - ADXIngestionBatching
description: Reference for ADXIngestionBatching table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# ADXIngestionBatching

Azure Data Explorer ingestion batching operations. These logs have detailed statistics of batches ready for ingestion (duration, batch size and blobs count).


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.kusto/clusters|
|**Categories**|-|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/adxingestionbatching)|



## Columns
  
[!INCLUDE [adxingestionbatching](./includes/adxingestionbatching-include.md)]
