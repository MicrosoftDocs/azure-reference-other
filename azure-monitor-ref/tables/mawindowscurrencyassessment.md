---
title: Azure Monitor Logs reference - MAWindowsCurrencyAssessment
description: Reference for MAWindowsCurrencyAssessment table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/09/2023
---

# MAWindowsCurrencyAssessment



## Categories

- Desktop Analytics
## Solutions

- Microsoft365Analytics




## Columns

| Column | Type | Description |
|---|---|---|
| AssessmentTime | datetime |   |
| _BilledSize | real | The record size in bytes |
| BuildId | int |   |
| BuildVersion | string |   |
| DeviceEOSDate | datetime |   |
| DeviceId | string |   |
| DeviceServicingLevel | string |   |
| FeatureCurrency | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastEventTime | datetime |   |
| ReleaseServicingLevel | string |   |
| ReleaseVersion | string |   |
| SecurityCompliance | string |   |
| ServicingChannel | string |   |
| ServicingState | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
