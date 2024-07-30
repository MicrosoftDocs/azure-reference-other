---
title: Azure Monitor Logs reference - AGSGrafanaLoginEvents
description: Reference for AGSGrafanaLoginEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AGSGrafanaLoginEvents

Login events for an instance of Azure Managed Workspace for Grafana including user identity, user Grafana role (in success) and detailed message (in failure).


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.dashboard/grafana|
|**Categories**|Azure Resources, Audit|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/agsgrafanaloginevents)|



## Columns
  
[!INCLUDE [agsgrafanaloginevents](./includes/agsgrafanaloginevents-include.md)]
