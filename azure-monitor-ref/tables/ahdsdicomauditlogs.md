---
title: Azure Monitor Logs reference - AHDSDicomAuditLogs
description: Reference for AHDSDicomAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# AHDSDicomAuditLogs

Data plane audit logs of privileged actions made against Azure Health Data DICOM service. For example, storing a DICOM instance.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.healthcareapis/workspaces|
|**Categories**|Audit, Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/ahdsdicomauditlogs)|



## Columns
  
[!INCLUDE [ahdsdicomauditlogs](.././tables/includes/ahdsdicomauditlogs-include.md)]
