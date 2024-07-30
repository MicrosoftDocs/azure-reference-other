---
title: Azure Monitor Logs reference - KubeMonAgentEvents
description: Reference for KubeMonAgentEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# KubeMonAgentEvents

Table that stores events from the Kubernetes cluster monitoring agent [Azure Monitor Agent]


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.kubernetes/connectedclusters,<br>microsoft.containerservice/managedclusters,<br>microsoft.hybridcontainerservice/provisionedclusters|
|**Categories**|Containers|
|**Solutions**| AzureResources, ContainerInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/kubemonagentevents)|



## Columns
  
[!INCLUDE [kubemonagentevents](./includes/kubemonagentevents-include.md)]
