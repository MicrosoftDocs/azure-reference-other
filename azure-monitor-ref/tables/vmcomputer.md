---
title: Azure Monitor Logs reference - VMComputer
description: Reference for VMComputer table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# VMComputer

Inventory data for servers collected by the Service Map and VM Insights solutions using the Dependency agent and Log analytics agent.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.compute/virtualmachines,<br>microsoft.conenctedvmwarevsphere/virtualmachines,<br>microsoft.azurestackhci/virtualmachines,<br>microsoft.scvmm/virtualmachines,<br>microsoft.compute/virtualmachinescalesets|
|**Categories**|Virtual Machines|
|**Solutions**| AzureResources, ServiceMap, VMInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [vmcomputer](.././tables/includes/vmcomputer-include.md)]
