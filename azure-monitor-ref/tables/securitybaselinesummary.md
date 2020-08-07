---
title: Azure Monitor Logs reference - SecurityBaselineSummary
description: Reference for SecurityBaselineSummary table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 7/30/2020
---

# SecurityBaselineSummary

 

## Categories

- Security
## Solutions

- Security and Audit
- SecurityCenter
- SecurityCenterFree
## Resource types

- Virtual machines




## Columns

|Column|Type|Description|
|---|---|---|
|AssessmentId|string||
|BaselineType|string||
|Computer|string||
|ComputerEnvironment|string||
|CriticalFailedRules|int||
|InformationalFailedRules|int||
|ManagementGroupName|string||
|OSName|string||
|PercentageOfPassedRules|int||
|Resource|string||
|ResourceGroup|string||
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ResourceId|string||
|ResourceProvider|string||
|ResourceType|string||
|SourceComputerId|string||
|SourceSystem|string||
|SubscriptionId|string||
|TimeGenerated|datetime||
|TotalAssessedRules|int||
|Type|string|The name of the table|
|WarningFailedRules|int||
