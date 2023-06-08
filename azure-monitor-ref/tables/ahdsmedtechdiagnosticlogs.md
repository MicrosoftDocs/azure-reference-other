---
title: Azure Monitor Logs reference - AHDSMedTechDiagnosticLogs
description: Reference for AHDSMedTechDiagnosticLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
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
| _BilledSize | real |  |
| _IsBillable | string |  |
| LogType | string | Type of the log entry. |
| Message | string | Description of the log entry. |
| OperationName | string | The operation stage of the service from which the log entry was generated. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time (UTC) when the log was created. |
| Type | string | The name of the table |
