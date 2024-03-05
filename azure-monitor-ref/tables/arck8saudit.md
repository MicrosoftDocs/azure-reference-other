---
title: Azure Monitor Logs reference - ArcK8sAudit
description: Reference for ArcK8sAudit table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# ArcK8sAudit

Contains all Kubernetes API Server audit logs including events with the get and list verbs. These events are useful for monitoring all of the interactions with the Kubernetes API. To limit the scope to modifying operations see the ArcK8sAuditAdmin table. Requires Diagnostic Settings to use the Resource Specific destination table.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.kubernetes/connectedclusters|
|**Categories**|Audit, Azure Resources, Containers|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [arck8saudit](.././tables/includes/arck8saudit-include.md)]
