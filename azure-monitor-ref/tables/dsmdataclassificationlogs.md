---
title: Azure Monitor Logs reference - DSMDataClassificationLogs
description: Reference for DSMDataClassificationLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# DSMDataClassificationLogs

 Contains data classification information provided by Azure Purview and is used to correlate storage resource logs with data sensitivity information.

## Categories

- Security
- Azure Resources
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AssetLastScanTime | datetime | The time (UTC) when the resource scan for sensitivity was performed by Azure Purview. |
| AssetType | string | Type of asset that was scanned by Azure Purview (e.g., File, Table). |
| ClassificationDetails | dynamic | For every classification found in the resource - corresponding Instance Count (i.e. how many occurrences of a specific type of classification was present) and Confidence (i.e. Match Accuracy) is listed. |
| Classifications | dynamic | JSON containing the list of classifications that were discovered. |
| CorrelationId | string | The ID that is used to correlate resource logs with data sensitivity logs. |
| SourceSystem | string |  |
| SourceType | string | Type of resource that was scanned by Azure Purview (Azure Blob, Azure File, etc.). |
| TenantId | string |  |
| TimeGenerated | datetime | The time (UTC) when Azure Purview scan of asset occurred. |
| Type | string | The name of the table |
| Uri | string | Uniform resource identifier representing the asset that was scanned. |
