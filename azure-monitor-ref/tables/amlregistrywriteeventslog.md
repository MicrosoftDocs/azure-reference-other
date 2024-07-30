---
title: Azure Monitor Logs reference - AmlRegistryWriteEventsLog
description: Reference for AmlRegistryWriteEventsLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AmlRegistryWriteEventsLog

Azure ML Registry Write events log. It keeps records of Write operations with registries data access (data plane), including user identity, asset name and version for each access event.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.machinelearningservices/registries|
|**Categories**|Audit, Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/amlregistrywriteeventslog)|



## Columns
  
[!INCLUDE [amlregistrywriteeventslog](./includes/amlregistrywriteeventslog-include.md)]
