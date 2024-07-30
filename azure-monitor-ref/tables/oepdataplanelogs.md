---
title: Azure Monitor Logs reference - OEPDataplaneLogs
description: Reference for OEPDataplaneLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# OEPDataplaneLogs

Contains logs for HTTP requests & responses for the Indexer Service API, in OSDU Data Platform, and Microsoft Energy Data Services. The Indexer service, indexes the metadata store to support search. The indexer service will automatically take items that are newly added to storage and index the attributes from the schema associated with the kind attribute.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.openenergyplatform/energyservices|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [oepdataplanelogs](./includes/oepdataplanelogs-include.md)]
