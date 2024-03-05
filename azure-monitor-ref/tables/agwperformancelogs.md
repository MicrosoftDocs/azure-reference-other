---
title: Azure Monitor Logs reference - AGWPerformanceLogs
description: Reference for AGWPerformanceLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# AGWPerformanceLogs

Contains all the logs to view how Application Gateway instances are performing. This log captures performance information for each instance, including total requests served, throughput in bytes, total requests served, failed request count, and healthy and unhealthy backend instance count.The Performance log is available only for the v1 SKU.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.network/applicationgateways|
|**Categories**|Azure Resources, Network, Audit|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [agwperformancelogs](.././tables/includes/agwperformancelogs-include.md)]
