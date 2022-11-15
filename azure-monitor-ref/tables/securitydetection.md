---
title: Azure Monitor Logs reference - SecurityDetection
description: Reference for SecurityDetection table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# SecurityDetection

 

## Categories

- Security
## Solutions

- Security and Audit




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccountsSeen | int |  |
| AlertSeverity | string |  |
| AlertTitle | string |  |
| AssociatedResource | string |  |
| ChildProcess | string |  |
| CommandLine | string |  |
| Computer | string |  |
| Description | string |  |
| DetectionID | string |  |
| Duration | string |  |
| ExtendedProperties | string |  |
| FailedAttempts | int |  |
| FullPath | string |  |
| InvalidAccountsSeen | int |  |
| IsFirstParty | bool |  |
| LogChannel | string |  |
| OccuringDatacenter | string |  |
| OriginalSeverity | string |  |
| ParentProcess | string |  |
| ProcessName | string |  |
| Provider | string |  |
| RemediationSteps | string |  |
| ReportingSystem | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ServiceId | string |  |
| SubjectDomainName | string |  |
| SubjectUserName | string |  |
| SubscriptionId | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SuccessfulLogins | int |  |
| SuspiciousProcess | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| ValidAccountsSeen | int |  |
