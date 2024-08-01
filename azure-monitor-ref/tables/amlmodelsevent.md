---
title: Azure Monitor Logs reference - AmlModelsEvent
description: Reference for AmlModelsEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AmlModelsEvent

Events when ML model is accessed (read, created, or deleted). Incudes events when packaging of models and assets happen into a ready-to-build packages.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.machinelearningservices/workspaces|
|**Categories**|Azure Resources, Audit|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/amlmodelsevent)|



## Columns
  
[!INCLUDE [amlmodelsevent](./includes/amlmodelsevent-include.md)]
