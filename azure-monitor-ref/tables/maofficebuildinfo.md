---
title: Azure Monitor Logs reference - MAOfficeBuildInfo
description: Reference for MAOfficeBuildInfo table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/09/2023
---

# MAOfficeBuildInfo



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
| FeatureCurrency | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| KBUrl | string |   |
| OfferedBuildType | string |   |
| ReleaseType | string |   |
| ReleaseVersion | string |   |
| SecurityCompliance | string |   |
| ServicingChannel | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
