---
title: Azure Monitor Logs reference - PowerBIDatasetsWorkspace
description: Reference for PowerBIDatasetsWorkspace table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# PowerBIDatasetsWorkspace

Contains Analysis Services engine process events such as the start of a batch or transaction e.g. execute query, process partition. Typically used to monitor the performance, health and usage of Power BI's data engine. Contains information from the entire tenant.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.powerbi/tenants/workspaces|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [powerbidatasetsworkspace](./includes/powerbidatasetsworkspace-include.md)]
