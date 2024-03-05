---
title: Azure Monitor Logs reference - VMBoundPort
description: Reference for VMBoundPort table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# VMBoundPort

Traffic for open server ports on the monitored machine.


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
  
[!INCLUDE [vmboundport](.././tables/includes/vmboundport-include.md)]
