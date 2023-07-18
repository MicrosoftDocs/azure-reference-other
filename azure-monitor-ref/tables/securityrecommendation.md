---
title: Azure Monitor Logs reference - SecurityRecommendation
description: Reference for SecurityRecommendation table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/17/2023
---

# SecurityRecommendation

 

## Categories

- Security
## Solutions

- AzureSecurityOfThings
- Security and Audit
- SecurityCenterFree




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AssessedResourceId | string |  |
| _BilledSize | real | The record size in bytes |
| Description | string |  |
| DeviceId | string |  |
| DiscoveredTimeUTC | datetime |  |
| Environment | string |  |
| FirstEvaluationDate | datetime |  |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| IsSnapshot | bool |  |
| PolicyDefinitionId | string |  |
| Properties | dynamic |  |
| ProviderName | string |  |
| RecommendationAdditionalData | dynamic |  |
| RecommendationDisplayName | string |  |
| RecommendationId | string |  |
| RecommendationName | string |  |
| RecommendationSeverity | string |  |
| RecommendationState | string |  |
| ResolvedTimeUTC | datetime |  |
| ResourceRegion | string |  |
| StatusChangeDate | datetime |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
