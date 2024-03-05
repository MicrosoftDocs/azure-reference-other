---
title: Azure Monitor Logs reference - ACSCallDiagnostics
description: Reference for ACSCallDiagnostics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# ACSCallDiagnostics

Diagnostics logs provide information about the media transfers that occur in a call. Every log corresponds to an individual media stream and contains information about the emitting endpoint (e.g. the user sending the stream).


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.communication/communicationservices|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/acscalldiagnostics)|



## Columns
  
[!INCLUDE [acscalldiagnostics](.././tables/includes/acscalldiagnostics-include.md)]
