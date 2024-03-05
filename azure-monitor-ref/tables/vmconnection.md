---
title: Azure Monitor Logs reference - VMConnection
description: Reference for VMConnection table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# VMConnection

Traffic for inbound and outbound connections to and from monitored computers.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.compute/virtualmachines,<br>microsoft.conenctedvmwarevsphere/virtualmachines,<br>microsoft.azurestackhci/virtualmachines,<br>microsoft.scvmm/virtualmachines,<br>microsoft.compute/virtualmachinescalesets|
|**Categories**|Virtual Machines|
|**Solutions**| AzureResources, InfrastructureInsights, ServiceMap, VMInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [vmconnection](.././tables/includes/vmconnection-include.md)]
