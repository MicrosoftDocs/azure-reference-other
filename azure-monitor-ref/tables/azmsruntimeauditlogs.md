---
title: Azure Monitor Logs reference - AZMSRunTimeAuditLogs
description: Reference for AZMSRunTimeAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
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
  
[!INCLUDE [azmsruntimeauditlogs](.././tables/includes/azmsruntimeauditlogs-include.md)]
