---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: MAOfficeCurrencyAssessment
---


| Column | Type | Description |
|---|---|---|
| AssessmentTime | datetime |   |
| _BilledSize | real | The record size in bytes |
| BuildId | int |   |
| BuildVersion | string |   |
| DeviceId | string |   |
| FeatureCurrency | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastEventTime | datetime |   |
| ReleaseVersion | string |   |
| SecurityCompliance | string |   |
| ServicingChannel | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
