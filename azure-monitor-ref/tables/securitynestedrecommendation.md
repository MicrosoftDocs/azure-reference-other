---
title: Azure Monitor Logs reference - SecurityNestedRecommendation
description: Reference for SecurityNestedRecommendation table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 7/30/2020
---

# SecurityNestedRecommendation

 Nested recommendations can be thought of as 'sub' recommendations grouped into a 'parent' recommendation. To view nested recommendations, open the 'parent' from the recommendations page. For example, if a vulnerability scan of your SQL databases returns 100 findings, each finding will be available as a nested recommendation within the parent recommendation 'Vulnerabilities on your SQL databases should be remediated'.

## Solutions

- Security and Audit
- SecurityCenter
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
|RecommendationName|string|Display name of the sub-assessment|
|RecommendationSeverity|string|The sub-assessment severity level|
|RecommendationState|string|The sub-assessment state|
|RecommendationSubscriptionId|string|Recommendation's subscription Id|
|RemidiationDescription|string|Information on how to remediate this sub-assessment|
|ResourceDetails|dynamic|Details of the resource that was assessed|
|ResourceGroup|string|Resource group name|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|The date and time the sub-assessment was generated|
|Type|string|Resource type|
|VulnerabilityId|string|Vulnerability Id|
