---
title: Azure Monitor Logs reference - WireData
description: Reference for WireData table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# WireData

Network data collected by the WireData solution using by the Dependency agent and Log analytics agent.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.compute/virtualmachines,<br>microsoft.conenctedvmwarevsphere/virtualmachines,<br>microsoft.azurestackhci/virtualmachines,<br>microsoft.scvmm/virtualmachines,<br>microsoft.compute/virtualmachinescalesets|
|**Categories**|Virtual Machines, Security|
|**Solutions**| WireData, WireData2|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/wiredata)|



## Columns
  
[!INCLUDE [wiredata](.././tables/includes/wiredata-include.md)]
