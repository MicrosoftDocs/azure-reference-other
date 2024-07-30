---
title: Azure Monitor Logs reference - W3CIISLog
description: Reference for W3CIISLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# W3CIISLog

Internet Information Server (IIS) log on Windows computers using the Log Analytics agent.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.compute/virtualmachines,<br>microsoft.conenctedvmwarevsphere/virtualmachines,<br>microsoft.azurestackhci/virtualmachines,<br>microsoft.scvmm/virtualmachines,<br>microsoft.compute/virtualmachinescalesets|
|**Categories**|IT & Management Tools, Virtual Machines|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/w3ciislog)|



## Columns
  
[!INCLUDE [w3ciislog](./includes/w3ciislog-include.md)]
