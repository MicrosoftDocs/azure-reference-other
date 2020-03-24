---
title: Azure Monitor Logs reference - ProtectionStatus
description: Reference for ProtectionStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# ProtectionStatus

 Antimalware installation info and security health status of the machine:

## Categories

- Security
## Solutions

- Antimalware Assessment
- Security and Audit
- SecurityCenter
- SecurityCenterFree
## Resource types

- Virtual machine
- Virtual machine scale set




## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime||
|SourceComputerId|string||
|DeviceName|string||
|DetectionId|string||
|Threat|string||
|ThreatStatusRank|int||
|ThreatStatus|string||
|ThreatStatusDetails|string||
|ProtectionStatusRank|int||
|ProtectionStatus|string||
|ProtectionStatusDetails|string||
|SignatureVersion|string||
|TypeofProtection|string||
|ScanDate|datetime||
|AMProductVersion|string||
|ManagementGroupName|string||
|Computer|string||
|ComputerIP_Hidden|string||
|ResourceId|string||
|ComputerEnvironment|string||
|Resource|string||
|SubscriptionId|string||
|ResourceGroup|string||
|ResourceProvider|string||
|ResourceType|string||
|VMUUID|string||
|Type|string||
|_ResourceId|string||
