---
title: Azure Monitor Logs reference - AZMSOperationalLogs
description: Reference for AZMSOperationalLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AZMSOperationalLogs

Captures all management operations that are performed on the Azure Event Hubs/Azure Service Bus namespace and its entities.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.servicebus/namespaces,<br>microsoft.eventhub/namespaces|
|**Categories**|Azure Resources, Audit|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/azmsoperationallogs)|



## Columns
  
[!INCLUDE [azmsoperationallogs](./includes/azmsoperationallogs-include.md)]
