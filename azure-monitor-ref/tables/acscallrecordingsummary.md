---
title: Azure Monitor Logs reference - ACSCallRecordingSummary
description: Reference for ACSCallRecordingSummary table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# ACSCallRecordingSummary

Call recording summary logs provide an overview about a recording maed through ACS. There is one log for every recording done, and logs contain information about the duration of the recording, the content (e.g. Audio-Video, Unmixed, Transcription, etc.) and format (e.g. WAV, MP4, etc) types used for the recording, as well as the end reason of recording.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.communication/communicationservices|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/acscallrecordingsummary)|



## Columns
  
[!INCLUDE [acscallrecordingsummary](./includes/acscallrecordingsummary-include.md)]
