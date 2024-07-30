---
title: Azure Monitor Logs reference - ContainerInventory
description: Reference for ContainerInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# ContainerInventory

Inventory of containers and their attributes that are monitored by the agent


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.kubernetes/connectedclusters,<br>microsoft.containerservice/managedclusters,<br>microsoft.hybridcontainerservice/provisionedclusters|
|**Categories**|Containers|
|**Solutions**| AzureResources, ContainerInsights, Containers|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/containerinventory)|



## Columns
  
[!INCLUDE [containerinventory](./includes/containerinventory-include.md)]
