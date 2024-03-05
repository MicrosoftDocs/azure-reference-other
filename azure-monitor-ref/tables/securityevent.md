---
title: Azure Monitor Logs reference - SecurityEvent
description: Reference for SecurityEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# SecurityEvent

Security events collected from windows machines by Azure Security Center or Azure Sentinel.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.securityinsights/securityinsights,<br>microsoft.compute/virtualmachines,<br>microsoft.conenctedvmwarevsphere/virtualmachines,<br>microsoft.azurestackhci/virtualmachines,<br>microsoft.scvmm/virtualmachines,<br>microsoft.compute/virtualmachinescalesets|
|**Categories**|Security|
|**Solutions**| Security, SecurityInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/securityevent)|



## Columns
  
[!INCLUDE [securityevent](.././tables/includes/securityevent-include.md)]
