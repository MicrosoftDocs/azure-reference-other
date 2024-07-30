---
title: Azure Monitor Logs reference - AGWAccessLogs
description: Reference for AGWAccessLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AGWAccessLogs

Contains all the log to view Application Gateway access patterns and analyze important information. This includes the caller's IP, requested URL, response latency, return code, and bytes in and out.


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
  
[!INCLUDE [agwaccesslogs](./includes/agwaccesslogs-include.md)]
