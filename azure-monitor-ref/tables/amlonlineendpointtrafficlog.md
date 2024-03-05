---
title: Azure Monitor Logs reference - AmlOnlineEndpointTrafficLog
description: Reference for AmlOnlineEndpointTrafficLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# AmlOnlineEndpointTrafficLog

Traffic logs for AzureML (machine learning) online endpoints. The table could be used to check the detailed information of the request to an online endpoint. For example, you could use it to check the request duration, the request failure reason, etc.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.machinelearningservices/workspaces|
|**Categories**|Audit, Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/amlonlineendpointtrafficlog)|



## Columns
  
[!INCLUDE [amlonlineendpointtrafficlog](.././tables/includes/amlonlineendpointtrafficlog-include.md)]
