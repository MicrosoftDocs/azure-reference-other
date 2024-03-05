---
title: Azure Monitor Logs reference - AMSLiveEventOperations
description: Reference for AMSLiveEventOperations table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# AMSLiveEventOperations

Contains logs related to a Live Event. Logs are sent when an encoder connects, disconnects, or if there is a discontinuity in the media data.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.media/mediaservices|
|**Categories**|Audit, Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/amsliveeventoperations)|



## Columns
  
[!INCLUDE [amsliveeventoperations](.././tables/includes/amsliveeventoperations-include.md)]
