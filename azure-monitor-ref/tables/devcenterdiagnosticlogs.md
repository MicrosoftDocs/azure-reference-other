---
title: Azure Monitor Logs reference - DevCenterDiagnosticLogs
description: Reference for DevCenterDiagnosticLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
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
  
[!INCLUDE [devcenterdiagnosticlogs](./includes/devcenterdiagnosticlogs-include.md)]
