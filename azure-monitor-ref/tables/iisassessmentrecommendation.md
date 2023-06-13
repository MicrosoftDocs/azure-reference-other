---
title: Azure Monitor Logs reference - IISAssessmentRecommendation
description: Reference for IISAssessmentRecommendation table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# IISAssessmentRecommendation

 

## Solutions

- IISAssessmentPlus




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActionArea | string |  |
| ActionAreaId | string |  |
| AffectedObjectName | string |  |
| AffectedObjectType | string |  |
| AssessmentId | string |  |
| _BilledSize | real |  |
| Computer | string |  |
| Description | string |  |
| FocusArea | string |  |
| FocusAreaId | string |  |
| IISApplication | string |  |
| IISApplicationPool | string |  |
| _IsBillable | string |  |
| Recommendation | string |  |
| RecommendationId | string |  |
| RecommendationResult | string |  |
| RecommendationWeight | real |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| WebServer | string |  |
| WebSite | string |  |
