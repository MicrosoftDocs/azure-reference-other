---
title: Azure Monitor Logs reference - UCServiceUpdateStatus
description: Reference for UCServiceUpdateStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# UCServiceUpdateStatus

Update Compliance - Update Event that comes directly from the service-side, and only tells the "service-side" of the story, for one device (client), and one update, in one deployment. As such, this event is stripped of certain fields in favor of being able to show data in near real-time.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|-|
|**Categories**|-|
|**Solutions**| LogManagement, WaaSUpdateInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [ucserviceupdatestatus](.././tables/includes/ucserviceupdatestatus-include.md)]
