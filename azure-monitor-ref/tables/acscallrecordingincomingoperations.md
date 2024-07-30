---
title: Azure Monitor Logs reference - ACSCallRecordingIncomingOperations
description: Reference for ACSCallRecordingIncomingOperations table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# ACSCallRecordingIncomingOperations

Communication Services logs of incoming requests to Call Recording operations. Every entry corresponds to the result of a call to the Call Recording APIs, e.g. StartRecording, StopRecording, PauseRecording, ResumeRecording, etc.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.communication/communicationservices|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/acscallrecordingincomingoperations)|



## Columns
  
[!INCLUDE [acscallrecordingincomingoperations](./includes/acscallrecordingincomingoperations-include.md)]
