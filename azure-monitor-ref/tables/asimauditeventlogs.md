---
title: Azure Monitor Logs reference - ASimAuditEventLogs
description: Reference for ASimAuditEventLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# ASimAuditEventLogs

Microsoft Sentinel normalized audit events table. Stores events associated with the audit trail of information systems and audit trail logs system configuration activities and policy changes. Such changes are often performed by system administrators, but can also be performed by users when configuring the settings of their own applications.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.securityinsights/auditeventnormalized|
|**Categories**|Security|
|**Solutions**| SecurityInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [asimauditeventlogs](.././tables/includes/asimauditeventlogs-include.md)]
