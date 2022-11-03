---
title: Azure Monitor Logs reference - SecureScores
description: Reference for SecureScores table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# SecureScores

 Azure Security Center overall Secure Scores per subscription.

## Solutions

- Security and Audit
- SecurityCenter
- SecurityCenterFree




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AssessedResourceId | string | The ID of the assessed resource |
| CurrentScore | real | The current secure score per control |
| DisplayName | string | The initiative�s name |
| Environment | string | Data source environment. |
| IsSnapshot | bool | Indicates whether the data was exported as part of a snapshot when 'true', or streamed in real-time when 'false'. |
| MaxScore | int | The maximum control score |
| PercentageScore | real | The percentage of the score (current score divided by max score) |
| Properties | dynamic | The complete set of metadata. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceProviderType | string | Resource provider type of the assessed resource |
| SecureScoresSubscriptionId | string | The ID of the subscription |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The (UTC) date and time the control score was generated |
| Type | string | The name of the table |
| Weight | long | The weight for calculation of an aggregated score for several scopes |
