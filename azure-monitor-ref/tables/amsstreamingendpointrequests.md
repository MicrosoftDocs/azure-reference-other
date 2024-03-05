---
title: Azure Monitor Logs reference - AMSStreamingEndpointRequests
description: Reference for AMSStreamingEndpointRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# AMSStreamingEndpointRequests

Contains information about requests to streaming endpoints. A streaming endpoint receives HTTP requests needed to stream video content. These requests usually come from video players or from the CDN.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.media/mediaservices|
|**Categories**|Audit, Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/amsstreamingendpointrequests)|



## Columns
  
[!INCLUDE [amsstreamingendpointrequests](.././tables/includes/amsstreamingendpointrequests-include.md)]
