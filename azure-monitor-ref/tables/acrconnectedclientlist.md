---
title: Azure Monitor Logs reference - ACRConnectedClientList
description: Reference for ACRConnectedClientList table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# ACRConnectedClientList

Logs count of Redis clients connected to a cache instance and their IP addresses, logged at a 10-second interval.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.cache/redis|
|**Categories**|Azure Resources, Audit|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/acrconnectedclientlist)|



## Columns
  
[!INCLUDE [acrconnectedclientlist](./includes/acrconnectedclientlist-include.md)]
