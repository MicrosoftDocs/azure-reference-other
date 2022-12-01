---
title: Azure Monitor Logs reference - SynapseLinkEvent
description: Reference for SynapseLinkEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# SynapseLinkEvent

 Information about Synapse Link, including Link status and Link table status.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Synapse Workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Level | int | The log type info level of the record. |
| LinkConnectionName | string | The Synapse Link connection name. |
| Location | string | The location of the resource in the cloud where this log is originated. |
| OperationName | string | The operation associated with log record. |
| Properties | dynamic | The properties associated with Synapse Link operation. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
