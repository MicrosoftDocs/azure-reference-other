---
title: Azure Monitor Logs reference - SecurityRegulatoryCompliance
description: Reference for SecurityRegulatoryCompliance table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# SecurityRegulatoryCompliance

 Azure Security Center regulatory compliance assessments state.

## Solutions

- Security and Audit
- SecurityCenter
- SecurityCenterFree




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AssessedResourceId | string | The ID of the assessed resource |
| ComplianceControl | string | The name of regulatory compliance control |
| ComplianceStandard | string | The name of compliance standard |
| FailedResources | int | The number of resources that failed this assessment |
| IsSnapshot | bool | Indicates whether the data was exported as part of a snapshot when 'true', or streamed in real-time when 'false'. |
| PassedResources | int | The number of resources that passed this assessment |
| Properties | dynamic | The complete set of metadata. |
| RecommendationId | string | The ID of the assessed recommendation |
| RecommendationLink | string | A link for more details on the assessment result |
| RecommendationName | string | Recommendation display name |
| RegulatoryComplianceSubscriptionId | string | The subscription ID of the assessed resource |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceProviderType | string | Resource provider type of the assessed resource |
| SkippedResources | int | The number of resources that passed this assessment |
| SourceSystem | string |  |
| State | string | The assessment state |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The (UTC) date and time the assessment was generated |
| Type | string | The name of the table |
