---
title: Azure Monitor Logs reference - MAWindowsCurrencyAssessmentDailyCounts
description: Reference for MAWindowsCurrencyAssessmentDailyCounts table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/09/2023
---

# MAWindowsCurrencyAssessmentDailyCounts



## Categories

- Desktop Analytics
## Solutions

- Microsoft365Analytics




## Columns

| Column | Type | Description |
|---|---|---|
| AggregationTime | datetime |   |
| _BilledSize | real | The record size in bytes |
| BuildId | int |   |
| BuildVersion | string |   |
| DeviceCount | int |   |
| FeatureCurrencyLegend | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ReleaseVersion | string |   |
| SecurityComplianceLegend | string |   |
| ServicingChannel | string |   |
| SnapshotTime | datetime |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
