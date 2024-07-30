---
title: Azure Monitor Logs reference - ACSCallClientMediaStatsTimeSeries
description: Reference for ACSCallClientMediaStatsTimeSeries table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# ACSCallClientMediaStatsTimeSeries

Call client media stats logs provide media statistics about a call made through ACS. These los are used to provide granular timeseries for quality metrics in Call Diagnostics Center. The logs contains information about media stream type, direction, codec as well as bitrate properties (e.g. max, min, average).


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.communication/communicationservices|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/acscallclientmediastatstimeseries)|



## Columns
  
[!INCLUDE [acscallclientmediastatstimeseries](./includes/acscallclientmediastatstimeseries-include.md)]
