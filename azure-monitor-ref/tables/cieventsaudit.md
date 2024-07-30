---
title: Azure Monitor Logs reference - CIEventsAudit
description: Reference for CIEventsAudit table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# CIEventsAudit

All API requests in the context of the Customer Insights instance, for example all user actions while configuring and using the instance. POST|PUT|DELETE|PATCH operations go into this category.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.d365customerinsights/instances|
|**Categories**|Azure Resources, Audit|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/cieventsaudit)|



## Columns
  
[!INCLUDE [cieventsaudit](./includes/cieventsaudit-include.md)]
