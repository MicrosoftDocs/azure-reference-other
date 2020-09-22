---
title: Azure Monitor Logs reference - SecurityBaselineSummary
description: Reference for SecurityBaselineSummary table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/17/2020
---

# SecurityBaselineSummary

 

## Categories

- Security
## Solutions

- SecurityCenterFree
- SecurityCenter
- Security and Audit
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
|ResourceId|string||
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ResourceProvider|string||
|ResourceType|string||
|SourceComputerId|string||
|SourceSystem|string||
|SubscriptionId|string||
|TimeGenerated|datetime||
|TotalAssessedRules|int||
|Type|string|The name of the table|
|WarningFailedRules|int||
