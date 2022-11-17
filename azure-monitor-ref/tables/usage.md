---
title: Azure Monitor Logs reference - Usage
description: Reference for Usage table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# Usage

 Hourly usage data for each table in the workspace.

## Categories

- Azure Monitor
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AvgLatencyInSeconds | real | Deprecated |
| BatchesCapped | long | Deprecated |
| BatchesOutsideSla | long | Deprecated |
| BatchesWithinSla | long | Deprecated |
| Computer | string | Deprecated |
| DataType | string | Table that usage is being reported about. |
| EndTime | datetime | End time of the one hour aggregation window. |
| IsBillable | bool | Logical flag to indicate whether we bill for this data record. |
| LinkedMeterId | string | Deprecated |
| LinkedResourceUri | string | Deprecated |
| MeterId | string | GUID of the meter used for billing. |
| Quantity | real | Size of data in Mbytes. |
| QuantityUnit | string | Value is alwais Mbytes. |
| ResourceUri | string | The URI of the workspace. This will be same for all records in this table in workspace. |
| Solution | string | Solution about which usage is being reported. |
| SourceSystem | string | For Usage record SourceSystem is always OMS. |
| StartTime | datetime | Start time of the 1 hour aggregation window (same as TimeGenerated). |
| TimeGenerated | datetime | Date and time the record was created. |
| TotalBatches | long | Deprecated |
| Type | string | The name of the table |
