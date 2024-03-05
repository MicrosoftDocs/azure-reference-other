---
title: Azure Monitor Logs reference - ApiManagementWebSocketConnectionLogs
description: Reference for ApiManagementWebSocketConnectionLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# ApiManagementWebSocketConnectionLogs

Websocket connection logs provides logs on websocket connection events for API Management Gateway. Logging starts when the request arrives to API Management Gateway for handshake and till the request gets terminated. Every request log can be uniquely identified with CorrelationId.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.apimanagement/service|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [apimanagementwebsocketconnectionlogs](.././tables/includes/apimanagementwebsocketconnectionlogs-include.md)]
