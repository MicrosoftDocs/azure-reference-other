---
title: Azure Monitor Logs reference - Alert
description: Reference for Alert table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 2/17/2022
---

# Alert

 Alerts created by log alerts rules and SCOM alerts collected through Alert Management solution.

## Categories

- Azure Monitor
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AlertDescription | string | Detailed description of the alert. |
| AlertName | string | Name of the alert. |
| AlertRuleId | string |  |
| AlertRuleInstanceId | string |  |
| AlertSeverity | string | Severity level of the alert. |
| AlertState | string | Latest resolution state of the alert. |
| Computer | string |  |
| LinkToSearchResults | string |  |
| ObjectDisplayName | string |  |
| Query | string |  |
| QueryExecutionEndTime | datetime |  |
| QueryExecutionStartTime | datetime |  |
| RemediationJobId | string |  |
| RemediationRunbookName | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceId | string |  |
| ResourceType | string |  |
| ResourceValue | string |  |
| RootObjectName | string |  |
| ServiceDeskConnectionName | string |  |
| ServiceDeskId | string |  |
| ServiceDeskWorkItemLink | string |  |
| ServiceDeskWorkItemType | string |  |
| SourceDisplayName | string | Display name of the monitoring object that generated the alert. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| ThresholdOperator | string |  |
| ThresholdValue | int |  |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
