---
title: Azure Monitor Logs reference - AZMSApplicationMetricLogs
description: Reference for AZMSApplicationMetricLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# AZMSApplicationMetricLogs

Captures application metrics(incoming/outgoing, successful/failed, etc. message delivery) for Azure Event Hubs and Azure Service Bus.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.servicebus/namespaces,<br>microsoft.eventhub/namespaces|
|**Categories**|Azure Resources, Audit|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [azmsapplicationmetriclogs](.././tables/includes/azmsapplicationmetriclogs-include.md)]
