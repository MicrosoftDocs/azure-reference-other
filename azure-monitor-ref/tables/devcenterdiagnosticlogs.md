---
title: Azure Monitor Logs reference - DevCenterDiagnosticLogs
description: Reference for DevCenterDiagnosticLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# DevCenterDiagnosticLogs

Data plane audit logs related to your dev center resources. Will display information concerning stop/start/deletes on dev boxes and environments.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.devcenter/devcenters|
|**Categories**|Audit, Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/devcenterdiagnosticlogs)|



## Columns
  
[!INCLUDE [devcenterdiagnosticlogs](.././tables/includes/devcenterdiagnosticlogs-include.md)]
