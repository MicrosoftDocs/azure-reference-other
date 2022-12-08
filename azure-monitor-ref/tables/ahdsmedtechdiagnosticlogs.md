---
title: Azure Monitor Logs reference - AHDSMedTechDiagnosticLogs
description: Reference for AHDSMedTechDiagnosticLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# AHDSMedTechDiagnosticLogs

 Actionable logs generated from your MedTech application.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Health Data Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| LogType | string | Type of the log entry. |
| Message | string | Description of the log entry. |
| OperationName | string | The operation stage of the service from which the log entry was generated. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time (UTC) when the log was created. |
| Type | string | The name of the table |
