---
title: Azure Monitor Logs reference - ConfigurationChange
description: Reference for ConfigurationChange table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# ConfigurationChange

View changes to in-guest configuration data such as Files Software Registry Keys Windows Services and Linux Daemons


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.compute/virtualmachines,<br>microsoft.conenctedvmwarevsphere/virtualmachines,<br>microsoft.azurestackhci/virtualmachines,<br>microsoft.scvmm/virtualmachines,<br>microsoft.compute/virtualmachinescalesets|
|**Categories**|IT & Management Tools|
|**Solutions**| ChangeTracking|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/configurationchange)|



## Columns
  
[!INCLUDE [configurationchange](./includes/configurationchange-include.md)]
