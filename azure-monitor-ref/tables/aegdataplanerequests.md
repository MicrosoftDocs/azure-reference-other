---
title: Azure Monitor Logs reference - AegDataPlaneRequests
description: Reference for AegDataPlaneRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# AegDataPlaneRequests

Logs for Event Grid data plane requests (publish and options) against a topic/domain/partnernamespace. It can be used for auditing purposes. Logs are aggregated over a minute and displays the total number of requests with specific request properties.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.eventgrid/topics,<br>microsoft.eventgrid/domains,<br>microsoft.eventgrid/partnernamespaces|
|**Categories**|Azure Resources, Audit|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/aegdataplanerequests)|



## Columns
  
[!INCLUDE [aegdataplanerequests](.././tables/includes/aegdataplanerequests-include.md)]
