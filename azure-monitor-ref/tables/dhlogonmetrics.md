---
title: Azure Monitor Logs reference - DHLogonMetrics
description: Reference for DHLogonMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/17/2023
---

# DHLogonMetrics

 

## Categories

- Desktop Analytics
## Solutions

- Device Health




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real | The record size in bytes |
| Computer | string |  |
| ComputerID | string |  |
| Country | string |  |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| Manufacturer | string |  |
| Model | string |  |
| ModelFamily | string |  |
| OSArchitecture | string |  |
| OSBuildNumber | int |  |
| OSEdition | string |  |
| OSRevisionNumber | int |  |
| OSVersion | string |  |
| PreferredSignInProviderId | string |  |
| PreferredSignInProviderName | string |  |
| ProviderId | string |  |
| ProviderName | string |  |
| SignInIndustrySuccessRate | real |  |
| SignInSuccessRate | real |  |
| TimeGenerated | datetime |  |
| TotalDailySignIns | long |  |
| Type | string | The name of the table |
