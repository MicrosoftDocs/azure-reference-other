---
title: Azure Monitor Logs reference - AZFWNetworkRule
description: Reference for AZFWNetworkRule table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AZFWNetworkRule

Contains all Network Rule log data. Each match between data plane and network rule creates a log entry with the data plane packet and the matched rule's attributes.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.network/azurefirewalls|
|**Categories**|Security|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/azfwnetworkrule)|



## Columns
  
[!INCLUDE [azfwnetworkrule](./includes/azfwnetworkrule-include.md)]
