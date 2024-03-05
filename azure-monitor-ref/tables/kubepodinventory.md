---
title: Azure Monitor Logs reference - KubePodInventory
description: Reference for KubePodInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# KubePodInventory

Table that stores kubernetes cluster's Pod & container information


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.kubernetes/connectedclusters,<br>microsoft.containerservice/managedclusters,<br>microsoft.hybridcontainerservice/provisionedclusters|
|**Categories**|Containers|
|**Solutions**| AzureResources, ContainerInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/kubepodinventory)|



## Columns
  
[!INCLUDE [kubepodinventory](.././tables/includes/kubepodinventory-include.md)]
