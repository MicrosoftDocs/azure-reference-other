---
title: Azure Monitor Logs reference - SecurityNestedRecommendation
description: Reference for SecurityNestedRecommendation table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 7/2/2020
---

# SecurityNestedRecommendation

 Nested-recommendations are individual recommendations that are part of a parent security recommendation. These can be, for example, individual system updates under the parent 'System updates should be installed on your machines' recommendation.

## Solutions

-  Security and Audit
- SecurityCenterFree




## Columns

|Column|Type|Description|
|---|---|---|
|AdditionalData|dynamic|Additional details of the sub-assessment|
|AssessedResourceId|string|Id of the assessed resource|
|Category|string|Category of the sub-assessment|
|Cause|string|Cause of the assessment status|
|Description|string|Description of the assessment status|
|Id|string|Id of the assessed recommendation|
|Impact|string|Description of the impact of this sub-assessment|
|NestedRecommendationId|string|Id of the nested-recommendation|
|ParentRecommendationId|string|Id of the parent recommendation|
|RecommendationLink|string|Recommendation link URL|
|RecommendationName|string|Id of the assessed recommendation|
|RecommendationSeverity|string|The sub-assessment severity level|
|RecommendationState|string|The sub-assessment state|
|RemidiationDescription|string|Information on how to remediate this sub-assessment|
|ResourceDetails|dynamic|Details of the resource that was assessed|
|ResourceGroup|string|Resource group name|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|The date and time the sub-assessment was generated|
|Type|string|Resource type|
|VulnerabilityId|string|Vulnerability Id|
