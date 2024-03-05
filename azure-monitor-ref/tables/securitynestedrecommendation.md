---
title: Azure Monitor Logs reference - SecurityNestedRecommendation
description: Reference for SecurityNestedRecommendation table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# SecurityNestedRecommendation

Nested recommendations can be thought of as 'sub' recommendations grouped into a 'parent' recommendation. To view nested recommendations, open the 'parent' from the recommendations page in Security Center. For example, if a vulnerability scan of your SQL databases returns 100 findings, each finding will be available as a nested recommendation within the parent recommendation 'Vulnerabilities on your SQL databases should be remediated'.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|-|
|**Categories**|-|
|**Solutions**| Security, SecurityCenter, SecurityCenterFree|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [securitynestedrecommendation](.././tables/includes/securitynestedrecommendation-include.md)]
