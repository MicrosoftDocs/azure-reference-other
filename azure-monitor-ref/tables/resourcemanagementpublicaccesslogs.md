---
title: Azure Monitor Logs reference - ResourceManagementPublicAccessLogs
description: Reference for ResourceManagementPublicAccessLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# ResourceManagementPublicAccessLogs

Contains Resource management private link analysis events such as the operations that are already blocked due to private link present at the scope or operations that would be blocked. Contains information from the entire tenant.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|-|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/resourcemanagementpublicaccesslogs)|



## Columns
  
[!INCLUDE [resourcemanagementpublicaccesslogs](.././tables/includes/resourcemanagementpublicaccesslogs-include.md)]
