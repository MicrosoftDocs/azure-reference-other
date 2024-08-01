---
title: Azure Monitor Logs reference - AZMSDiagnosticErrorLogs
description: Reference for AZMSDiagnosticErrorLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AZMSDiagnosticErrorLogs

Captures aggregated diagnostic information such as client errors , server busy errors and quota exceeded errors for various data plane access operations (such as send or receive messages) in Azure Event Hubs and Azure Service Bus.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.servicebus/namespaces,<br>microsoft.eventhub/namespaces|
|**Categories**|Audit|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/azmsdiagnosticerrorlogs)|



## Columns
  
[!INCLUDE [azmsdiagnosticerrorlogs](./includes/azmsdiagnosticerrorlogs-include.md)]
