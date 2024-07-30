---
title: Azure Monitor Logs reference - ACSCallClosedCaptionsSummary
description: Reference for ACSCallClosedCaptionsSummary table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# ACSCallClosedCaptionsSummary

Call closed captions summary logs provide an overview about a closed captions made through ACS. There is one log for every closed captions done, and logs contain information about the duration of the closed captions, start time, spoken language and end reason, as well as the cancel reason of closed captions.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.communication/communicationservices|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [acscallclosedcaptionssummary](./includes/acscallclosedcaptionssummary-include.md)]
