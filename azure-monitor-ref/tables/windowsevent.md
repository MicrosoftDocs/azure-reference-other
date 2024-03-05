---
title: Azure Monitor Logs reference - WindowsEvent
description: Reference for WindowsEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# WindowsEvent

Windows events which are collected and sent by the agent.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|-|
|**Categories**|Security|
|**Solutions**| CustomizedWindowsEventsFiltering, InternalWindowsEvent, SecurityInsights, WEFInternalUat, WEF_10x, WEF_10xDSRE, WinLog, WindowsEventForwarding|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/windowsevent)|



## Columns
  
[!INCLUDE [windowsevent](.././tables/includes/windowsevent-include.md)]
