---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SecurityDetection
---


| Column | Type | Description |
|---|---|---|
| AccountsSeen | int |   |
| AlertSeverity | string |   |
| AlertTitle | string |   |
| AssociatedResource | string |   |
| _BilledSize | real | The record size in bytes |
| ChildProcess | string |   |
| CommandLine | string |   |
| Computer | string |   |
| Description | string |   |
| DetectionID | string |   |
| Duration | string |   |
| ExtendedProperties | string |   |
| FailedAttempts | int |   |
| FullPath | string |   |
| InvalidAccountsSeen | int |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsFirstParty | bool |   |
| LogChannel | string |   |
| OccuringDatacenter | string |   |
| OriginalSeverity | string |   |
| ParentProcess | string |   |
| ProcessName | string |   |
| Provider | string |   |
| RemediationSteps | string |   |
| ReportingSystem | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ServiceId | string |   |
| SubjectDomainName | string |   |
| SubjectUserName | string |   |
| SubscriptionId | string |   |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SuccessfulLogins | int |   |
| SuspiciousProcess | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| ValidAccountsSeen | int |   |
