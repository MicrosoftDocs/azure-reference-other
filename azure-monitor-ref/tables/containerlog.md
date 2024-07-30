---
title: Azure Monitor Logs reference - ContainerLog
description: Reference for ContainerLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# ContainerLog

Log lines collected from stdout and stderr streams for containers.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.kubernetes/connectedclusters,<br>microsoft.containerservice/managedclusters,<br>microsoft.compute/virtualmachines,<br>microsoft.conenctedvmwarevsphere/virtualmachines,<br>microsoft.azurestackhci/virtualmachines,<br>microsoft.scvmm/virtualmachines,<br>microsoft.compute/virtualmachinescalesets,<br>microsoft.hybridcontainerservice/provisionedclusters|
|**Categories**|Containers, Applications|
|**Solutions**| AzureResources, ContainerInsights, Containers|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/containerlog)|



## Columns
  
[!INCLUDE [containerlog](./includes/containerlog-include.md)]
