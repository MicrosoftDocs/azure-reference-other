---
title: Azure Monitor Logs reference - UpdateSummary
description: Reference for UpdateSummary table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/17/2020
---

# UpdateSummary

 Summary for each update schedule run. Includes information such as how many updates were not installed.

## Categories

- Virtual Machines
## Solutions

- SecurityCenterFree
- Update Management
- Security and Audit
- SecurityCenter
## Resource types

- Virtual Machine Scale Sets
- Virtual machines




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
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
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
|Type|string|The name of the table|
|VMUUID|string||
|WindowsUpdateAgentVersion|string||
|WindowsUpdateSetting|string||
|WSUSServer|string||
