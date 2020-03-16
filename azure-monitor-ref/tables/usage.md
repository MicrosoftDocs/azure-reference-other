---
title: Azure Monitor Logs reference - Usage
description: Reference for Usage table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# Usage

 Hourly usage data for each table in the workspace.

## Categories

- Azure Monitor
## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|Computer|string|Deprecated|
|TimeGenerated|datetime|Date and time the record was created.|
|SourceSystem|string|For Usage record SourceSystem is always OMS.|
|StartTime|datetime|Start time of the 1 hour aggregation window (same as TimeGenerated).|
|EndTime|datetime|End time of the one hour aggregation window.|
|ResourceUri|string|The URI of the workspace. This will be same for all records in this table in workspace.|
|LinkedResourceUri|string|Deprecated|
|DataType|string|Table that usage is being reported about.|
|Solution|string|Solution about which usage is being reported.|
|BatchesWithinSla|long|Deprecated|
|BatchesOutsideSla|long|Deprecated|
|BatchesCapped|long|Deprecated|
|TotalBatches|long|Deprecated|
|AvgLatencyInSeconds|real|Deprecated|
|Quantity|real|Size of data in Mbytes.|
|QuantityUnit|string|Value is alwais Mbytes.|
|IsBillable|bool|Logical flag to indicate whether we bill for this data record.|
|MeterId|string|GUID of the meter used for billing.|
|LinkedMeterId|string|Deprecated|
|Type|string||
