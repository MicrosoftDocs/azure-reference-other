---
title: Azure Monitor Logs reference - AGCAccessLogs
description: Reference for AGCAccessLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# AGCAccessLogs

Contains details of client requests made to Application Gateway for Containers. Each client request creats a log entry that can be used to identify slow requests, determine error rates, and correlate logs with backend services.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.servicenetworking/trafficcontrollers|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/agcaccesslogs)|



## Columns
  
[!INCLUDE [agcaccesslogs](.././tables/includes/agcaccesslogs-include.md)]
