---
title: Azure Monitor Logs reference - AFSAuditLogs
description: Reference for AFSAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# AFSAuditLogs

This table contains audit logs retrieved from your Azure Managed Lustre filesystem resource. These logs capture all priviledged operations performed on each Azure Managed Lustre resource. They can be used to monitor events and configure alerts on your resource.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.storagecache/amlfilesytems|
|**Categories**|Audit, Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/afsauditlogs)|



## Columns
  
[!INCLUDE [afsauditlogs](./includes/afsauditlogs-include.md)]
