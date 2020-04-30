---
title: Azure Monitor Logs reference - UpdateSummary
description: Reference for UpdateSummary table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# UpdateSummary

 Summary for each update schedule run. Includes information such as how many updates were not installed.

## Categories

- Virtual Machines
## Solutions

- Security and Audit
- SecurityCenter
- SecurityCenterFree
- Update Management
## Resource types

- Virtual machine
- Virtual machine scale set




## Columns

|Column|Type|Description|
|---|---|---|
|Computer|string||
|ComputerEnvironment|string||
|CriticalUpdatesMissing|int||
|ManagementGroupName|string||
|NETRuntimeVersion|string||
|OldestMissingSecurityUpdateBucket|string||
|OldestMissingSecurityUpdateInDays|int||
|OsVersion|string||
|OtherUpdatesMissing|int||
|Resource|string||
|ResourceGroup|string||
|_ResourceId|string||
|ResourceId|string||
|ResourceProvider|string||
|ResourceType|string||
|RestartPending|bool||
|SecurityUpdatesMissing|int||
|SourceComputerId|string||
|SourceSystem|string||
|SubscriptionId|string||
|TimeGenerated|datetime||
|TotalUpdatesMissing|int||
|Type|string||
|VMUUID|string||
|WindowsUpdateAgentVersion|string||
|WindowsUpdateSetting|string||
|WSUSServer|string||
