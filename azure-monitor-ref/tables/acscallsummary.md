---
title: Azure Monitor Logs reference - ACSCallSummary
description: Reference for ACSCallSummary table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# ACSCallSummary

Call summary logs provide an overview about a call made through ACS. There is one log for every participant in the call, and logs contain information about the duration of the call, the duration of the individual participant, the type of participant (e.g. VoIP, PSTN, etc.), as well as the endpoint information like the OS version being used, or the SDK version of the ACS platform.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.communication/communicationservices|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/acscallsummary)|



## Columns
  
[!INCLUDE [acscallsummary](.././tables/includes/acscallsummary-include.md)]
