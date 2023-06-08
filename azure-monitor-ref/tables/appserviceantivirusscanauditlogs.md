---
title: Azure Monitor Logs reference - AppServiceAntivirusScanAuditLogs
description: Reference for AppServiceAntivirusScanAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AppServiceAntivirusScanAuditLogs

 Report on any discovered virus or infected files that have been uploaded to their site.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Category | string | Log category name |
| ErrorMessage | string | Error Message |
| _IsBillable | string |  |
| ListOfInfectedFiles | string | List of each virus file path |
| NumberOfInfectedFiles | int | Total number of files infected with virus |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ScanStatus | string | Status of the scan |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time when event is generated |
| TimeStamp | datetime | Time when event is generated |
| TotalFilesScanned | int | Total number of scanned files |
| Type | string | The name of the table |
