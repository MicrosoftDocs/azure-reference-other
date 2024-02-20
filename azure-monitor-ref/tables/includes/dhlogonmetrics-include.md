---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: DHLogonMetrics
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Computer | string |   |
| ComputerID | string |   |
| Country | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Manufacturer | string |   |
| Model | string |   |
| ModelFamily | string |   |
| OSArchitecture | string |   |
| OSBuildNumber | int |   |
| OSEdition | string |   |
| OSRevisionNumber | int |   |
| OSVersion | string |   |
| PreferredSignInProviderId | string |   |
| PreferredSignInProviderName | string |   |
| ProviderId | string |   |
| ProviderName | string |   |
| SignInIndustrySuccessRate | real |   |
| SignInSuccessRate | real |   |
| TimeGenerated | datetime |   |
| TotalDailySignIns | long |   |
| Type | string | The name of the table |
