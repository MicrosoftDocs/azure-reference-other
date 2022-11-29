---
title: Azure Monitor Logs reference - SecureScoreControls
description: Reference for SecureScoreControls table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# SecureScoreControls

 Azure Security Center Secure Score per control. A control is a logical group of related security recommendations, its secure score reflects the security posture per the control.

## Solutions

- Security and Audit
- SecurityCenter
- SecurityCenterFree




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AssessedResourceId | string | The ID of the assessed resource |
| ControlId | string | The ID of the assessed control |
| ControlName | string | The display name of the control |
| ControlType | string | The type of security control (for example, BuiltIn) |
| CurrentScore | real | The current secure score per control |
| Description | string | The description of the control |
| Environment | string | Data source environment. |
| HealthyResources | int | The number of healthy resources |
| IsSnapshot | bool | Indicates whether the data was exported as part of a snapshot when 'true', or streamed in real-time when 'false'. |
| MaxScore | int | The maximum control score |
| NotApplicableResources | int | The number of not applicable resources |
| PercentageScore | real | The percentage of the score (current score divided by max score) |
| Properties | dynamic | The complete set of metadata. |
| RecommendationResourceIds | dynamic | The recommendation resource IDs for the recommendations assessed in the control |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceProviderType | string | Resource provider type of the assessed resource |
| SecureScoresSubscriptionId | string | The ID of the subscription |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The (UTC) date and time the control score was generated |
| Type | string | The name of the table |
| UnhealthyResources | int | The number of unhealthy resources |
| Weight | long | The weight for calculation of an aggregated score for several scopes |
