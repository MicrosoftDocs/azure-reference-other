---
title: Azure Monitor Logs reference - AOIDigestion
description: Reference for AOIDigestion table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AOIDigestion

Logs related to digestion of files added to the input storage account. These can be used to verify that data is being successfully passed through to enrichment, or to troubleshoot issues with processing the raw data.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.networkanalytics/dataproducts|
|**Categories**|-|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/aoidigestion)|



## Columns
  
[!INCLUDE [aoidigestion](./includes/aoidigestion-include.md)]
