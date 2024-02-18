---
title: Azure Monitor Logs reference - UserAccessAnalytics
description: Reference for UserAccessAnalytics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024
---

# UserAccessAnalytics

This analytics table, for a given user, provides the direct or transitive access to Azure resources. For example, if the user under investigation is Jane Smith, Access Analytics calculates all the Azure subscriptions that she either can access directly, via groups or serviceprincipals.


## Categories

- Security

## Solutions

- BehaviorAnalyticsInsights

## Columns
  
[!INCLUDE [useraccessanalytics](.././tables/includes/useraccessanalytics-include.md)]
