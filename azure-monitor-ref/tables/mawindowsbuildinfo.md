---
title: Azure Monitor Logs reference - MAWindowsBuildInfo
description: Reference for MAWindowsBuildInfo table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/09/2023
---

# MAWindowsBuildInfo



## Categories

- Desktop Analytics
## Solutions

- Microsoft365Analytics




## Columns

| Column | Type | Description |
|---|---|---|
| AvailabilityDate | datetime |   |
| _BilledSize | real | The record size in bytes |
| BuildId | int |   |
| BuildVersion | string |   |
| EOSDate | datetime |   |
| ExtEOSDate | datetime |   |
| FeatureCurrencyExtended | string |   |
| FeatureCurrencyPaid | string |   |
| FeatureCurrencyStandard | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| KB | string |   |
| KBUrl | string |   |
| OfferedBuildType | string |   |
| PaidEOSDate | datetime |   |
| ReleaseType | string |   |
| ReleaseVersion | string |   |
| SecurityCompliance | string |   |
| ServicingChannel | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
