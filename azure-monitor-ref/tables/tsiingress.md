---
title: Azure Monitor Logs reference - TSIIngress
description: Reference for TSIIngress table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# TSIIngress

The Ingress category tracks errors that occur in the ingress pipeline. This category includes errors that occur when receiving events (such as failures to connect to an Event Source) and processing events (such as errors when parsing an event payload).


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.timeseriesinsights/environments|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/tsiingress)|



## Columns
  
[!INCLUDE [tsiingress](./includes/tsiingress-include.md)]
