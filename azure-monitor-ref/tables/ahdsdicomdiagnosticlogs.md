---
title: Azure Monitor Logs reference - AHDSDicomDiagnosticLogs
description: Reference for AHDSDicomDiagnosticLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AHDSDicomDiagnosticLogs

 Actionable logs generated from your Azure Health Data DICOM service, including events information like, warning logs per tag per DICOM instance denoting validation issues.

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
| CorrelationId | string | An identifier used to group together a set of related events. |
| _IsBillable | string |  |
| Location | string | Azure region of service from which log was generated. Examples are 'eastus', 'centralindia', 'westus2', etc. |
| LogLevel | string | The log's severity level. Possible values are Informational, Warning, and Error. |
| Message | string | Description of the log entry. |
| OperationName | string | The operation name for which the log entry was generated. For example, Store/PostInstance/POST |
| Properties | dynamic | Additional information about the event in JSON array format. Examples include DICOM identifiers present in the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time (UTC) when the log was created. |
| Type | string | The name of the table |
