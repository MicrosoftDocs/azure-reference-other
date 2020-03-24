---
title: Azure Monitor Logs reference - SecurityDetection
description: Reference for SecurityDetection table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# SecurityDetection

 

## Categories

- Security
## Solutions

- Security and Audit




## Columns

|Column|Type|Description|
|---|---|---|
|TimeGenerated|datetime||
|Computer|string||
|Provider|string||
|AlertTitle|string||
|AlertSeverity|string||
|Description|string||
|RemediationSteps|string||
|OriginalSeverity|string||
|DetectionID|string||
|SubjectUserName|string||
|SubjectDomainName|string||
|ProcessName|string||
|CommandLine|string||
|LogChannel|string||
|Duration|string||
|InvalidAccountsSeen|int||
|ValidAccountsSeen|int||
|SuccessfulLogins|int||
|FailedAttempts|int||
|AccountsSeen|int||
|SuspiciousProcess|string||
|FullPath|string||
|ChildProcess|string||
|ParentProcess|string||
|ExtendedProperties|string||
|SubscriptionId|string||
|ServiceId|string||
|IsFirstParty|bool||
|ReportingSystem|string||
|OccuringDatacenter|string||
|AssociatedResource|string||
|Type|string||
|_ResourceId|string||
