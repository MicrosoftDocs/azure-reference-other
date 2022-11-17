---
title: Azure Monitor Logs reference - SecurityBaseline
description: Reference for SecurityBaseline table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# SecurityBaseline

 

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
- Virtual Machine Scale Sets




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActualResult | string |  |
| AnalyzeOperation | string |  |
| AnalyzeResult | string |  |
| AssessmentId | string |  |
| AzId | string |  |
| BaselineRuleType | string |  |
| BaselineType | string |  |
| CceId | string |  |
| Computer | string |  |
| ComputerEnvironment | string |  |
| Description | string |  |
| ExpectedResult | string |  |
| ManagementGroupName | string |  |
| OSName | string |  |
| Resource | string |  |
| ResourceGroup | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceId | string |  |
| ResourceProvider | string |  |
| ResourceType | string |  |
| RuleSetting | string |  |
| RuleSeverity | string |  |
| SitePath | string |  |
| SourceComputerId | string |  |
| SourceSystem | string |  |
| SubscriptionId | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
