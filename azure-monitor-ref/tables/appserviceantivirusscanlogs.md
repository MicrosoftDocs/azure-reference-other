---
title: Azure Monitor Logs reference - AppServiceAntivirusScanLogs
description: Reference for AppServiceAntivirusScanLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 6/1/2021
---

# AppServiceAntivirusScanLogs

 Report on any discovered virus or infected files that have been uploaded to their site.

## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|Category|string|Log category name|
|ErrorMessage|string|Error Message|
|ListOfInfectedFiles|string|List of each virus file path|
|NumberOfInfectedFiles|int|Total number of virus files|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ScanStatus|string|Status of the scan|
|SourceSystem|string||
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TenantId|string||
|TimeGenerated|datetime||
|TimeStamp|datetime|Time when event is generated|
|TotalFilesScanned|int|Total number of files scanned|
|Type|string|The name of the table|
