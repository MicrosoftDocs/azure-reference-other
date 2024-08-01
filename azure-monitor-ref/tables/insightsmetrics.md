---
title: Azure Monitor Logs reference - InsightsMetrics
description: Reference for InsightsMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# InsightsMetrics

Table that stores metrics. 'Perf' table also stores many metrics and over time they all will converge to InsightsMetrics for Azure Monitor Solutions 


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.kubernetes/connectedclusters,<br>microsoft.containerservice/managedclusters,<br>microsoft.insights/workloadmonitoring,<br>microsoft.compute/virtualmachines,<br>microsoft.conenctedvmwarevsphere/virtualmachines,<br>microsoft.azurestackhci/virtualmachines,<br>microsoft.scvmm/virtualmachines,<br>microsoft.compute/virtualmachinescalesets,<br>microsoft.hybridcontainerservice/provisionedclusters,<br>microsoft.devices/iothubs|
|**Categories**|Virtual Machines, Containers, Azure Resources|
|**Solutions**| AzureResources, ContainerInsights, InfrastructureInsights, LogManagement, ServiceMap, VMInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/insightsmetrics)|



## Columns
  
[!INCLUDE [insightsmetrics](./includes/insightsmetrics-include.md)]
