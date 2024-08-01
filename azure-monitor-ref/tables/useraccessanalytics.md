---
title: Azure Monitor Logs reference - UserAccessAnalytics
description: Reference for UserAccessAnalytics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# UserAccessAnalytics

This analytics table, for a given user, provides the direct or transitive access to Azure resources. For example, if the user under investigation is Jane Smith, Access Analytics calculates all the Azure subscriptions that she either can access directly, via groups or serviceprincipals.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|-|
|**Categories**|Security|
|**Solutions**| BehaviorAnalyticsInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [useraccessanalytics](./includes/useraccessanalytics-include.md)]
