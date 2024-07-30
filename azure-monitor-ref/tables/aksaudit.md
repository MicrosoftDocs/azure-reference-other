---
title: Azure Monitor Logs reference - AKSAudit
description: Reference for AKSAudit table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AKSAudit

Contains all Kubernetes API Server audit logs including events with the get and list verbs. These events are useful for monitoring all of the interactions with the Kubernetes API. To limit the scope to modifying operations see the AKSAuditAdmin table.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.containerservice/managedclusters|
|**Categories**|Audit, Azure Resources, Containers|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/aksaudit)|



## Columns
  
[!INCLUDE [aksaudit](./includes/aksaudit-include.md)]
