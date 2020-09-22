---
title: Azure Monitor Logs reference - ProtectionStatus
description: Reference for ProtectionStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/17/2020
---

# ProtectionStatus

 Antimalware installation info and security health status of the machine:

## Categories

- Security
## Solutions

- SecurityCenter
- SecurityCenterFree
- Antimalware Assessment
- Security and Audit
## Resource types

- Virtual Machine Scale Sets
- Virtual machines




## Columns

|Column|Type|Description|
|---|---|---|
|AMProductVersion|string||
|Computer|string||
|ComputerEnvironment|string||
|ComputerIP_Hidden|string||
|DetectionId|string||
|DeviceName|string||
|ManagementGroupName|string||
|ProtectionStatus|string||
|ProtectionStatusDetails|string||
|ProtectionStatusRank|int||
|Resource|string||
|ResourceGroup|string||
|ResourceId|string||
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ResourceProvider|string||
|ResourceType|string||
|ScanDate|datetime||
|SignatureVersion|string||
|SourceComputerId|string||
|SourceSystem|string||
|SubscriptionId|string||
|TenantId|string||
|Threat|string||
|ThreatStatus|string||
|ThreatStatusDetails|string||
|ThreatStatusRank|int||
|TimeGenerated|datetime||
|Type|string|The name of the table|
|TypeofProtection|string||
|VMUUID|string||
