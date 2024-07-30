---
title: Azure Monitor Logs reference - Heartbeat
description: Reference for Heartbeat table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# Heartbeat

Records logged by Log Analytics agents once per minute to report on agent health.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.compute/virtualmachines,<br>microsoft.kubernetes/connectedclusters,<br>microsoft.containerservice/managedclusters,<br>microsoft.conenctedvmwarevsphere/virtualmachines,<br>microsoft.azurestackhci/virtualmachines,<br>microsoft.scvmm/virtualmachines,<br>microsoft.compute/virtualmachinescalesets,<br>microsoft.hybridcontainerservice/provisionedclusters,<br>microsoft.automation/automationaccounts|
|**Categories**|Virtual Machines, Containers, IT & Management Tools|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/heartbeat)|



## Columns
  
[!INCLUDE [heartbeat](./includes/heartbeat-include.md)]
