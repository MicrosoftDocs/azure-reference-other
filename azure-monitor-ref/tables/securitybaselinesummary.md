---
title: Azure Monitor Logs reference - SecurityBaselineSummary
description: Reference for SecurityBaselineSummary table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 5/26/2023
---

# SecurityBaselineSummary

 

## Categories

- Security
## Solutions

- Security and Audit
- SecurityCenter
- SecurityCenterFree
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AssessmentId | string |  |
| BaselineType | string |  |
| _BilledSize | real |  |
| Computer | string |  |
| ComputerEnvironment | string |  |
| CriticalFailedRules | int |  |
| InformationalFailedRules | int |  |
| _IsBillable | string |  |
| ManagementGroupName | string |  |
| OSName | string |  |
| PercentageOfPassedRules | int |  |
| Resource | string |  |
| ResourceGroup | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceId | string |  |
| ResourceProvider | string |  |
| ResourceType | string |  |
| SourceComputerId | string |  |
| SourceSystem | string |  |
| SubscriptionId | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| TotalAssessedRules | int |  |
| Type | string | The name of the table |
| WarningFailedRules | int |  |
