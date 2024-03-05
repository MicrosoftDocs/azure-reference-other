---
title: Azure Monitor Logs reference - WebPubSubMessaging
description: Reference for WebPubSubMessaging table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# WebPubSubMessaging

Messaging logs provide tracing information for the Azure Web PubSub hub messages received and sent via Azure Web PubSub service. For example, tracing ID and message type of the message. Typically the message is recorded when it arrives at or leaves from service and is helpful for troubleshooting message-related issues.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.signalrservice/webpubsub|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [webpubsubmessaging](.././tables/includes/webpubsubmessaging-include.md)]
