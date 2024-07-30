---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: MAWindowsCurrencyAssessment
---


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
