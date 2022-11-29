---
title: Azure Monitor Logs reference - DSMDataLabelingLogs
description: Reference for DSMDataLabelingLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# DSMDataLabelingLogs

 Contains data sensitivity labeling information provided by Azure Purview and  is used to correlate storage resource logs with data sensitivity information.

## Categories

- Security
- Azure Resources
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AssetLastScanTime | datetime | The time (UTC) when the resource scan for sensitivity was performed by Azure Purview. |
| CorrelationId | string | The ID that is used to correlate resource logs with data sensitivity logs. |
| SensitivityLabelName | string | The name of sensitive label found and/or applied. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | The time (UTC) when Azure Purview scan of asset occurred. |
| Type | string | The name of the table |
| Uri | string | Uniform resource identifier representing the resource that was scanned. |
