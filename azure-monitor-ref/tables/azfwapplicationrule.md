---
title: Azure Monitor Logs reference - AZFWApplicationRule
description: Reference for AZFWApplicationRule table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AZFWApplicationRule

Contains all Application rule log data. Each match between data plane and Application rule creates a log entry with the data plane packet and the matched rule's attributes.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.network/azurefirewalls|
|**Categories**|Security|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/azfwapplicationrule)|



## Columns
  
[!INCLUDE [azfwapplicationrule](./includes/azfwapplicationrule-include.md)]
