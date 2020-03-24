---
title: Azure Monitor Logs reference - Update
description: Reference for Update table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# Update

 Details for update schedule run. Includes information such as which updates where available and which were installed.

## Categories

- IT & Management Tools
- Security
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
|Title|string||
|MSRCSeverity|string||
|Classification|string||
|PublishedDate|datetime||
|Computer|string||
|UpdateState|string||
|Product|string||
|KBID|string||
|UpdateID|string||
|RevisionNumber|string||
|Optional|bool||
|RebootBehavior|string||
|MSRCBulletinID|string||
|Approved|bool||
|ApprovalSource|string||
|InstallTimePredictionSeconds|real||
|InstallTimeDeviationRangeSeconds|real||
|InstallTimeAvailable|bool||
|SubscriptionId|string||
|ResourceGroup|string||
|ResourceProvider|string||
|Resource|string||
|ResourceId|string||
|ResourceType|string||
|ComputerEnvironment|string||
|VMUUID|string||
|OSType|string||
|ProductVersion|string||
|ProductArch|string||
|CVENumbers|string||
|BulletinUrl|string||
|BulletinID|string||
|PackageRepository|string||
|PackageSeverity|string||
|OSName|string||
|OSVersion|string||
|OSFullName|string||
|Type|string||
|_ResourceId|string||
