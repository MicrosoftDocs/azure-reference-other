---
title: Azure Monitor Logs reference - Perf
description: Reference for Perf table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# Perf

Performance counters from Windows and Linux agents that provide insight into the performance of hardware components operating systems and applications.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.kubernetes/connectedclusters,<br>microsoft.containerservice/managedclusters,<br>microsoft.compute/virtualmachines,<br>microsoft.conenctedvmwarevsphere/virtualmachines,<br>microsoft.azurestackhci/virtualmachines,<br>microsoft.scvmm/virtualmachines,<br>microsoft.compute/virtualmachinescalesets,<br>microsoft.azurestackhci/clusters,<br>microsoft.hybridcontainerservice/provisionedclusters|
|**Categories**|Virtual Machines, Containers|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/perf)|



## Columns
  
[!INCLUDE [perf](.././tables/includes/perf-include.md)]
