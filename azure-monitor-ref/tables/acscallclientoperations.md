---
title: Azure Monitor Logs reference - ACSCallClientOperations
description: Reference for ACSCallClientOperations table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# ACSCallClientOperations

Call client operation logs provide information regarding operations performed by clients using the Azure Communication Service Calling client SDK. It includes information regarding events raised by the SDK, such as state changes, e.g. createView, startAudio,DevicePermissionRequest. This log will be used by Call Diagnostics Center to visualize a call flow in a time series manner.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.communication/communicationservices|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/acscallclientoperations)|



## Columns
  
[!INCLUDE [acscallclientoperations](.././tables/includes/acscallclientoperations-include.md)]
