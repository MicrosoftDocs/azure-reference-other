---
title: Azure Monitor Logs reference - AppServiceAntivirusScanAuditLogs
description: Reference for AppServiceAntivirusScanAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# AppServiceAntivirusScanAuditLogs

 Report on any discovered virus or infected files that have been uploaded to their site.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ErrorMessage | string | Error Message |
| ListOfInfectedFiles | string | List of each virus file path |
| NumberOfInfectedFiles | int | Total number of files infected with virus |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ScanStatus | string | Status of the scan |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time when event is generated |
| TotalFilesScanned | int | Total number of scanned files |
| Type | string | The name of the table |
