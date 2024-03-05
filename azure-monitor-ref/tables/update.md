---
title: Azure Monitor Logs reference - Update
description: Reference for Update table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# Update

Details for update schedule run. Includes information such as which updates where available and which were installed.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.compute/virtualmachines,<br>microsoft.conenctedvmwarevsphere/virtualmachines,<br>microsoft.azurestackhci/virtualmachines,<br>microsoft.scvmm/virtualmachines,<br>microsoft.compute/virtualmachinescalesets,<br>microsoft.automation/automationaccounts|
|**Categories**|IT & Management Tools, Security|
|**Solutions**| Security, SecurityCenter, SecurityCenterFree, Updates|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/update)|



## Columns
  
[!INCLUDE [update](.././tables/includes/update-include.md)]
