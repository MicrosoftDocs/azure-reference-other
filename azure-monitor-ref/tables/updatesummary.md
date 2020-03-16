---
title: Azure Monitor Logs reference - UpdateSummary
description: Reference for UpdateSummary table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
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
|SourceSystem|string||
|TimeGenerated|datetime||
|ManagementGroupName|string||
|SourceComputerId|string||
|OldestMissingSecurityUpdateInDays|int||
|OldestMissingSecurityUpdateBucket|string||
|WindowsUpdateSetting|string||
|WindowsUpdateAgentVersion|string||
|WSUSServer|string||
|Computer|string||
|OsVersion|string||
|NETRuntimeVersion|string||
|CriticalUpdatesMissing|int||
|SecurityUpdatesMissing|int||
|OtherUpdatesMissing|int||
|TotalUpdatesMissing|int||
|RestartPending|bool||
|SubscriptionId|string||
|ResourceGroup|string||
|ResourceProvider|string||
|Resource|string||
|ResourceId|string||
|ResourceType|string||
|ComputerEnvironment|string||
|VMUUID|string||
|Type|string||
|_ResourceId|string||
