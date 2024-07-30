---
title: Azure Monitor Logs reference - HealthStateChangeEvent
description: Reference for HealthStateChangeEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# HealthStateChangeEvent

Workload Monitor Health. This data represents state transitions of a health monitor.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.compute/virtualmachines,<br>microsoft.conenctedvmwarevsphere/virtualmachines,<br>microsoft.azurestackhci/virtualmachines,<br>microsoft.scvmm/virtualmachines|
|**Categories**|-|
|**Solutions**| AzureResources, VMInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [healthstatechangeevent](./includes/healthstatechangeevent-include.md)]
