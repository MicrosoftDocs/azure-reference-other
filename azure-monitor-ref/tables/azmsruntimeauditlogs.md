---
title: Azure Monitor Logs reference - AZMSRunTimeAuditLogs
description: Reference for AZMSRunTimeAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AZMSRunTimeAuditLogs

Captures aggregated diagnostic information for various data plane access operations (such as send or receive messages) in Azure Event Hubs and Azure Service Bus. Runtime audit logs are currently available only in premium tier.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.servicebus/namespaces,<br>microsoft.eventhub/namespaces|
|**Categories**|Audit|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/azmsruntimeauditlogs)|



## Columns
  
[!INCLUDE [azmsruntimeauditlogs](./includes/azmsruntimeauditlogs-include.md)]
