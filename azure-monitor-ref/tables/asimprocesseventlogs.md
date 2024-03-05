---
title: Azure Monitor Logs reference - ASimProcessEventLogs
description: Reference for ASimProcessEventLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# ASimProcessEventLogs

The Microsoft Sentinel process events normalized table stores events using the Process Event ASIM normalized schema associated with creation or termination of a process. Such events are reported by operating systems and security systems, such as EDR (End Point Detection and Response) systems.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.securityinsights/processeventnormalized|
|**Categories**|Security|
|**Solutions**| SecurityInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [asimprocesseventlogs](.././tables/includes/asimprocesseventlogs-include.md)]
