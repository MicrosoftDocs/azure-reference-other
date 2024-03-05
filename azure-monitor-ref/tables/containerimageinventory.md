---
title: Azure Monitor Logs reference - ContainerImageInventory
description: Reference for ContainerImageInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# ContainerImageInventory

Inventory of container images and their attributes that were discovered by the agent.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.kubernetes/connectedclusters,<br>microsoft.containerservice/managedclusters,<br>microsoft.hybridcontainerservice/provisionedclusters|
|**Categories**|Containers|
|**Solutions**| AzureResources, ContainerInsights, Containers|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/containerimageinventory)|



## Columns
  
[!INCLUDE [containerimageinventory](.././tables/includes/containerimageinventory-include.md)]
