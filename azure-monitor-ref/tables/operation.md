---
title: Azure Monitor Logs reference - Operation
description: Reference for Operation table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# Operation

 Operational log of important activities affecting workspace. Includes both user-initiated activities and notifications from Log Analytics workspace services such as data-capping.

## Categories

- Azure Monitor
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Computer | string | Name of a physical or virtual machine having membership with Log Analytics agent. |
| CorrelationId | string | GUID that is shared with telemetry belonging to the same uber action. |
| Detail | string | User friendly string that describes further details about the operation |
| ErrorId | string | Deprecated. |
| HelpLink | string | Reference URL for additional contextual information. |
| ManagementGroupName | string | Name of the Operations Manager management group for System Center Operations Manager agents. |
| OperationCategory | string | Name of the area that produced the record. |
| OperationKey | string | Operation ID. Can be a GUID or string. |
| OperationStatus | string | Operation status description. Ccommon values include Warning Succeeded Failed Error. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Solution | string | Name of the managed solution that produced the record. Can also include other sources such as RestAPI. |
| SourceComputerId | string | Unique GUID identifier for a computer. |
| SourceSystem | string | Value is OpsManager for all records in this table. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time that the record was created. |
| Type | string | The name of the table |
