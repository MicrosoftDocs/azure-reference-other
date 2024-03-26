---
title: Azure Monitor Logs reference - AKSControlPlane
description: Reference for AKSControlPlane table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/26/2024
---

# AKSControlPlane

Contains diagnostic logs for the Kubernetes API Server, Controller Manager, Scheduler, Cluster Autoscaler, Cloud Controller Manager, Guard, and the Azure CSI storage drivers. These diagnostic logs have distinct Category entries corresponding their diagnostic log setting (e.g. kube-apiserver, kube-audit-admin).


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.containerservice/managedclusters|
|**Categories**|Azure Resources, Containers|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/akscontrolplane)|



## Columns
  
[!INCLUDE [akscontrolplane](.././tables/includes/akscontrolplane-include.md)]
